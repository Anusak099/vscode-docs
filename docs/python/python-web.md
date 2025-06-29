---
ContentId: 366e4bbf-fa87-4813-9dfc-6c831b20a4d2
DateApproved: 06/12/2025
MetaDescription: Run and Debug Python code in the Web.
---
# Run and Debug Python in the Web

We are happy to announce **experimental** support for running Python code on the Web. To try it out, install the latest pre-release version of the [Experimental - Python for the Web](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-python-web-wasm) extension from the Marketplace. This work is based on WASM in Python, which is currently in development. To learn more about how it works and the ongoing progress, you can read [Compiling Python to WebAssembly (WASM)](https://pythondev.readthedocs.io/wasm.html).

## Prerequisites

The following prerequisites are needed to use the extension:

* You need to have the [GitHub Repositories](https://marketplace.visualstudio.com/items?itemName=GitHub.remotehub) extension installed.
* You need to authenticate with GitHub.
* You need to use a browser that supports [cross-origin isolation](https://developer.chrome.com/docs/extensions/mv3/cross-origin-isolation/). The extension has been tested with the Microsoft Edge and Google Chrome browsers.
* You need to use the insider version of [VS Code for the Web](/docs/setup/vscode-web.md) (for example `https://insiders.vscode.dev/`)
* Your source code must be hosted either on your local file system or a GitHub repository that is accessed through the [GitHub Repositories](https://marketplace.visualstudio.com/items?itemName=GitHub.remotehub) extension.
* When starting [VS Code for the Web](/docs/setup/vscode-web.md), you need to add the following query parameter to the end of the URL: `?vscode-coi=`.

## Run Hello World

The screenshot below shows the execution of a simple Python program in the browser. The program consists of two files `app.py` and `hello.py` stored on the local file system.

![Execution of Python code stored on a local disk](images/web/execution-local-files.png)

## Start a REPL

The extension comes with an integrated Python REPL. To activate it, run the command **Python WASM: Start REPL**.

![Start Python Repl](images/web/repl.png)

## Debugging

There is support for debugging Python files on the Web and it uses the same UI as VS Code Desktop [debugging](/docs/python/debugging.md). The features currently supported are:

* Set breakpoints
* Step into and out of functions
* Debug across modules
* Evaluate variables in the Debug Console
* Debug the program in the Integrated Terminal

The screenshot below shows an active debug session. The files are hosted directly on GitHub on this [sample repository](https://github.com/dbaeumer/python-sample).

![Debugging a Python program](images/web/debug.png)

## Create your own Python environment

The extension uses a pre-configured Python environment based on the [CPython WebAssembly builds](https://github.com/tiran/cpython-wasm-test/releases). The build used is `Python-3.11.0-wasm32-wasi-16.zip`.

You can create your own Python environment, including source wheel Python packages, following these steps:

* Create a new GitHub repository.
* Download a wasm-wasi-16 build from [cpython-wasm-test/releases](https://github.com/tiran/cpython-wasm-test/releases) and expand it into the root of the repository.
* To add source wheel packages, do the following:
  * Create a `site-packages` folder in the root.
  * Install the package using the following command `pip install my_package --target ./site-packages`. Note that you need to have a Python installation in your OS including pip.
* Commit the changes.
* Change the `python.wasm.runtime` setting to point to your GitHub repository. For example:

  ```json
  {
    "python.wasm.runtime": "https://github.com/dbaeumer/python-3.11.0"
  }
  ```

## Limitations

The Python for the Web support doesn't provide all the features available when running source code on your local machine. The major limitations in the Python interpreter are:

* No socket support.
* No thread support. As a consequence, there is no async support.
* No pip support.
* No support for native Python modules.

## Acknowledgment

The work would have not been possible without the support of the Python community, who are building and maintaining the necessary WASM files of CPython.

## Feedback

If you run into issues while using the Python for the Web extension, you can enter issues in the [vscode-python-web-wasm](https://github.com/microsoft/vscode-python-web-wasm) repository.
import React, { useState, useEffect } from 'react';
import { BarChart, Bar, XAxis, YAxis, CartesianGrid, Tooltip, ResponsiveContainer, LineChart, Line, PieChart, Pie, Cell } from 'recharts';
import { AlertTriangle, TrendingUp, TrendingDown, RefreshCw, Bell, Download } from 'lucide-react';

const RiskMonitoringCore = () => {
  // === CORE STATE MANAGEMENT ===
  const [activeTab, setActiveTab] = useState('dashboard');
  const [riskData, setRiskData] = useState({
    kri: [],
    alerts: [],
    summary: { high: 0, medium: 0, low: 0, total: 0 }
  });
  const [loading, setLoading] = useState(false);
  const [notifications, setNotifications] = useState([]);

  // === CORE DATA STRUCTURE ===
  const mockRiskData = {
    kri: [
      { id: 1, name: 'Credit Risk', value: 75, threshold: 80, status: 'normal', trend: 'stable' },
      { id: 2, name: 'Market Risk', value: 85, threshold: 80, status: 'warning', trend: 'rising' },
      { id: 3, name: 'Operational Risk', value: 60, threshold: 70, status: 'normal', trend: 'falling' }
    ],
    alerts: [
      { id: 1, message: 'Market Risk เกินเกณฑ์', level: 'high', timestamp: new Date() },
      { id: 2, message: 'Credit Risk ใกล้เกณฑ์', level: 'medium', timestamp: new Date() }
    ],
    summary: { high: 1, medium: 2, low: 0, total: 3 }
  };

  // === CORE FUNCTIONS ===

  // Data Management
  const loadRiskData = async () => {
    setLoading(true);
    try {
      // จำลองการดึงข้อมูลจาก API
      await new Promise(resolve => setTimeout(resolve, 1000));
      setRiskData(mockRiskData);
      addNotification('ข้อมูลได้รับการอัพเดท', 'success');
    } catch (error) {
      addNotification('เกิดข้อผิดพลาดในการโหลดข้อมูล', 'error');
    } finally {
      setLoading(false);
    }
  };

  // Notification System
  const addNotification = (message, type = 'info') => {
    const notification = {
      id: Date.now(),
      message,
      type,
      timestamp: new Date().toLocaleTimeString('th-TH')
    };
    setNotifications(prev => [notification, ...prev.slice(0, 4)]);

    // Auto remove after 5 seconds
    setTimeout(() => {
      setNotifications(prev => prev.filter(n => n.id !== notification.id));
    }, 5000);
  };

  // Risk Analysis
  const calculateRiskScore = (value, threshold) => {
    const ratio = value / threshold;
    if (ratio >= 1) return 'high';
    if (ratio >= 0.8) return 'medium';
    return 'low';
  };

  const getRiskColor = (status) => {
    switch (status) {
      case 'high': return '#EF4444';
      case 'warning': return '#F59E0B';
      case 'normal': return '#10B981';
      default: return '#6B7280';
    }
  };

  const getTrendIcon = (trend) => {
    switch (trend) {
      case 'rising': return <TrendingUp className="w-4 h-4 text-red-500" />;
      case 'falling': return <TrendingDown className="w-4 h-4 text-green-500" />;
      default: return <div className="w-4 h-4 bg-gray-400 rounded-full"></div>;
    }
  };

  // Report Generation
  const generateReport = (type) => {
    addNotification(`กำลังสร้างรายงาน ${type}...`, 'info');

    // จำลองการสร้างรายงาน
    setTimeout(() => {
      const reportData = {
        type,
        data: riskData,
        timestamp: new Date().toISOString(),
        summary: `รายงาน ${type} ณ วันที่ ${new Date().toLocaleDateString('th-TH')}`
      };

      // ในการใช้งานจริงจะส่งข้อมูลไปยัง API
      console.log('Generated Report:', reportData);
      addNotification(`สร้างรายงาน ${type} เสร็จสิ้น`, 'success');
    }, 2000);
  };

  // === CORE COMPONENTS ===

  // Risk Summary Card
  const RiskSummaryCard = ({ title, value, color, icon: Icon }) => (
    <div className="bg-white p-6 rounded-lg shadow-sm border">
      <div className="flex items-center">
        <div className={`p-3 rounded-lg bg-${color}-100`}>
          <Icon className={`w-6 h-6 text-${color}-600`} />
        </div>
        <div className="ml-4">
          <p className="text-sm font-medium text-gray-600">{title}</p>
          <p className="text-2xl font-bold text-gray-900">{value}</p>
        </div>
      </div>
    </div>
  );

  // KRI Table
  const KRITable = ({ data }) => (
    <div className="bg-white rounded-lg shadow-sm border overflow-hidden">
      <div className="px-6 py-4 border-b border-gray-200">
        <h3 className="text-lg font-medium text-gray-900">Key Risk Indicators</h3>
      </div>
      <div className="overflow-x-auto">
        <table className="min-w-full divide-y divide-gray-200">
          <thead className="bg-gray-50">
            <tr>
              <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">ตัวชี้วัด</th>
              <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">ค่าปัจจุบัน</th>
              <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">เกณฑ์</th>
              <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">แนวโน้ม</th>
              <th className="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase">สถานะ</th>
            </tr>
          </thead>
          <tbody className="bg-white divide-y divide-gray-200">
            {data.map((item) => (
              <tr key={item.id}>
                <td className="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">
                  {item.name}
                </td>
                <td className="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
                  {item.value}%
                </td>
                <td className="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
                  {item.threshold}%
                </td>
                <td className="px-6 py-4 whitespace-nowrap">
                  {getTrendIcon(item.trend)}
                </td>
                <td className="px-6 py-4 whitespace-nowrap">
                  <span className={`inline-flex px-2 py-1 text-xs font-semibold rounded-full ${
                    item.status === 'warning' ? 'bg-yellow-100 text-yellow-800' :
                    item.status === 'normal' ? 'bg-green-100 text-green-800' :
                    'bg-red-100 text-red-800'
                  }`}>
                    {item.status === 'warning' ? 'เตือน' :
                     item.status === 'normal' ? 'ปกติ' : 'เสี่ยง'}
                  </span>
                </td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );

  // Risk Chart
  const RiskChart = ({ data }) => (
    <div className="bg-white p-6 rounded-lg shadow-sm border">
      <h3 className="text-lg font-medium text-gray-900 mb-4">Risk Trend</h3>
      <ResponsiveContainer width="100%" height={300}>
        <LineChart data={data}>
          <CartesianGrid strokeDasharray="3 3" />
          <XAxis dataKey="name" />
          <YAxis />
          <Tooltip />
          <Line
            type="monotone"
            dataKey="value"
            stroke="#3B82F6"
            strokeWidth={2}
          />
          <Line
            type="monotone"
            dataKey="threshold"
            stroke="#EF4444"
            strokeDasharray="5 5"
          />
        </LineChart>
      </ResponsiveContainer>
    </div>
  );

  // Alert Panel
  const AlertPanel = ({ alerts }) => (
    <div className="bg-white rounded-lg shadow-sm border">
      <div className="px-6 py-4 border-b border-gray-200">
        <h3 className="text-lg font-medium text-gray-900">การแจ้งเตือน</h3>
      </div>
      <div className="p-6 space-y-4">
        {alerts.map((alert) => (
          <div key={alert.id} className={`p-4 rounded-lg border-l-4 ${
            alert.level === 'high' ? 'border-red-500 bg-red-50' :
            alert.level === 'medium' ? 'border-yellow-500 bg-yellow-50' :
            'border-blue-500 bg-blue-50'
          }`}>
            <div className="flex items-center">
              <AlertTriangle className={`w-5 h-5 mr-2 ${
                alert.level === 'high' ? 'text-red-600' :
                alert.level === 'medium' ? 'text-yellow-600' :
                'text-blue-600'
              }`} />
              <span className="font-medium">{alert.message}</span>
            </div>
            <p className="text-sm text-gray-600 mt-1">
              {alert.timestamp.toLocaleString('th-TH')}
            </p>
          </div>
        ))}
      </div>
    </div>
  );

  // === LIFECYCLE ===
  useEffect(() => {
    loadRiskData();
  }, []);

  // === RENDER ===
  return (
    <div className="min-h-screen bg-gray-50">
      {/* Header */}
      <div className="bg-white shadow-sm">
        <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
          <div className="flex justify-between items-center py-6">
            <div>
              <h1 className="text-2xl font-bold text-gray-900">Risk Monitoring System</h1>
              <p className="text-gray-600">ระบบติดตามความเสี่ยงแบบเรียลไทม์</p>
            </div>
            <div className="flex space-x-4">
              <button
                onClick={loadRiskData}
                disabled={loading}
                className="flex items-center px-4 py-2 bg-blue-600 text-white rounded-md hover:bg-blue-700 disabled:opacity-50"
              >
                <RefreshCw className={`w-4 h-4 mr-2 ${loading ? 'animate-spin' : ''}`} />
                {loading ? 'กำลังโหลด...' : 'รีเฟรช'}
              </button>
              <button
                onClick={() => generateReport('dashboard')}
                className="flex items-center px-4 py-2 bg-green-600 text-white rounded-md hover:bg-green-700"
              >
                <Download className="w-4 h-4 mr-2" />
                ส่งออกรายงาน
              </button>
            </div>
          </div>
        </div>
      </div>

      {/* Main Content */}
      <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
        <div className="space-y-8">

          {/* Summary Cards */}
          <div className="grid grid-cols-1 md:grid-cols-4 gap-6">
            <RiskSummaryCard
              title="ความเสี่ยงสูง"
              value={riskData.summary.high}
              color="red"
              icon={AlertTriangle}
            />
            <RiskSummaryCard
              title="ความเสี่ยงปานกลาง"
              value={riskData.summary.medium}
              color="yellow"
              icon={AlertTriangle}
            />
            <RiskSummaryCard
              title="ความเสี่ยงต่ำ"
              value={riskData.summary.low}
              color="green"
              icon={AlertTriangle}
            />
            <RiskSummaryCard
              title="รวมทั้งหมด"
              value={riskData.summary.total}
              color="blue"
              icon={TrendingUp}
            />
          </div>

          {/* Charts and Tables */}
          <div className="grid grid-cols-1 lg:grid-cols-2 gap-8">
            <KRITable data={riskData.kri} />
            <RiskChart data={riskData.kri} />
          </div>

          {/* Alerts */}
          <AlertPanel alerts={riskData.alerts} />
        </div>
      </div>

      {/* Notifications */}
      {notifications.length > 0 && (
        <div className="fixed top-4 right-4 z-50 space-y-2">
          {notifications.map((notification) => (
            <div
              key={notification.id}
              className={`p-4 rounded-lg shadow-lg max-w-sm text-white ${
                notification.type === 'success' ? 'bg-green-500' :
                notification.type === 'error' ? 'bg-red-500' :
                'bg-blue-500'
              }`}
            >
              <div className="flex items-center justify-between">
                <div className="flex items-center">
                  <Bell className="w-4 h-4 mr-2" />
                  <span className="text-sm">{notification.message}</span>
                </div>
                <button
                  onClick={() => setNotifications(prev => prev.filter(n => n.id !== notification.id))}
                  className="text-white hover:text-gray-200"
                >
                  ×
                </button>
              </div>
              <div className="text-xs opacity-75 mt-1">{notification.timestamp}</div>
            </div>
          ))}
        </div>
      )}
    </div>
  );
};

export default RiskMonitoringCore;