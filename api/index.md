---
# DO NOT TOUCH — Managed by doc writer
ContentId: AD26EFB1-FFC6-4284-BAB8-F3BCB8294728
DateApproved: 06/12/2025

# Summarize the whole topic in less than 300 characters for SEO purpose
MetaDescription: Visual Studio Code has a rich extension API. Learn how to create your own extensions for VS Code.
---

# Extension API

Visual Studio Code is built with extensibility in mind. From the UI to the editing experience, almost every part of VS Code can be customized and enhanced through the Extension API. In fact, many core features of VS Code are built as [extensions](https://github.com/microsoft/vscode/tree/main/extensions) and use the same Extension API.

This documentation describes:

* How to build, run, debug, test, and publish an extension
* How to take advantage of VS Code's rich Extension API
* Where to find [guides](https://code.visualstudio.com/api/extension-guides/overview) and [code samples](https://github.com/microsoft/vscode-extension-samples) to help get you started
* Following our [UX guidelines](/api/ux-guidelines/overview) for best practices

Code samples are available at [Microsoft/vscode-extension-samples](https://github.com/microsoft/vscode-extension-samples).

If you are looking for published extensions, head to the [VS Code Extension Marketplace](https://marketplace.visualstudio.com/vscode).

## What can extensions do?

Here are some examples of what you can achieve with the Extension API:

* Change the look of VS Code with a color or file icon theme - [Theming](/api/extension-capabilities/theming)
* Add custom components & views in the UI - [Extending the Workbench](/api/extension-capabilities/extending-workbench)
* Create a Webview to display a custom webpage built with HTML/CSS/JS - [Webview Guide](/api/extension-guides/webview)
* Support a new programming language - [Language Extensions Overview](/api/language-extensions/overview)
* Support debugging a specific runtime - [Debugger Extension Guide](/api/extension-guides/debugger-extension)

If you'd like to have a more comprehensive overview of the Extension API, refer to the [Extension Capabilities Overview](/api/extension-capabilities/overview) page. [Extension Guides Overview](/api/extension-guides/overview) also includes a list of code samples and guides that illustrate various Extension API usage.

## How to build extensions?

Building a good extension can take a lot of time and effort. Here is what each section of the API docs can help you with:

* **Get Started** teaches fundamental concepts for building extensions with the [Hello World](https://github.com/microsoft/vscode-extension-samples/tree/main/helloworld-sample) sample.
* **Extension Capabilities** dissects VS Code's vast API into smaller categories and points you to more detailed topics.
* **Extension Guides** includes guides and code samples that explain specific usages of VS Code Extension API.
* **UX Guidelines** showcases best practices for providing a great user experience in an extension.
* **Language Extensions** illustrates how to add support for a programming language with guides and code samples.
* **Testing and Publishing** includes in-depth guides on various extension development topics, such as [testing](/api/working-with-extensions/testing-extension) and [publishing](/api/working-with-extensions/publishing-extension) extensions.
* **Advanced Topics** explains advanced concepts such as [Extension Host](/api/advanced-topics/extension-host), [Supporting Remote Development and GitHub Codespaces](/api/advanced-topics/remote-extensions), and [Proposed API](/api/advanced-topics/using-proposed-api).
* **References** contains exhaustive references for the [VS Code API](/api/references/vscode-api), [Contribution Points](/api/references/contribution-points), and many other topics.

## What's new?

VS Code updates on a monthly cadence, and that applies to the Extension API as well. New features and APIs become available every month to increase the power and scope of VS Code extensions.

To stay current with the Extension API, you can review the monthly release notes, which have dedicated sections covering:

* [Extension authoring](https://code.visualstudio.com/updates#_extension-authoring) - Learn what new extension APIs are available in the latest release.
* [Proposed extension APIs](https://code.visualstudio.com/updates#_proposed-extension-apis) - Review and give feedback on upcoming proposed APIs.

## Looking for help

If you have questions for extension development, try asking on:

* [VS Code Discussions](https://github.com/microsoft/vscode-discussions): GitHub community to discuss VS Code's extension platform, ask questions, help other members of the community, and get answers.
* [Stack Overflow](https://stackoverflow.com/questions/tagged/vscode-extensions): There are [thousands of questions](https://stackoverflow.com/questions/tagged/vscode-extensions) tagged `vscode-extensions`, and over half of them already have answers. Search for your issue, ask questions, or help your fellow developers by answering VS Code extension development questions!
* [VS Code Dev Slack](https://vscode-dev-community.slack.com): Public chatroom for extension developers. VS Code team members often join in the conversations.

To provide feedback on the documentation, create new issues at [Microsoft/vscode-docs](https://github.com/microsoft/vscode-docs/issues).
If you have extension questions that you cannot find an answer for, or issues with the VS Code Extension API, please open new issues at [Microsoft/vscode](https://github.com/microsoft/vscode/issues).
2025-06-29 00:17:34.131 [trace] Remote configuration data at /home/codespace/.vscode-remote
2025-06-29 00:17:34.131 [trace] process arguments: {"_":[],"host":"127.0.0.1","port":"0","connection-token-file":"/home/codespace/.vscode-remote/data/Machine/.connection-token-2901c5ac6db8a986a5666c3af51ff804d05af0d4","without-connection-token":false,"disable-websocket-compression":false,"print-startup-performance":false,"print-ip-address":false,"accept-server-license-terms":true,"server-data-dir":"/home/codespace/.vscode-remote","enable-smoke-test-driver":false,"disable-telemetry":false,"disable-workspace-trust":false,"log":["trace"],"force-disable-user-env":true,"enable-sync":false,"use-test-resolver":false,"extensions-download-dir":"/home/codespace/.vscode-remote/extensionsCache","install-builtin-extension":["GitHub.vscode-pull-request-github","github.github-vscode-theme","github.copilot","github.copilot-chat","github.codespaces"],"update-extensions":false,"list-extensions":false,"show-versions":false,"force":false,"do-not-sync":true,"do-not-include-pack-dependencies":false,"pre-release":false,"start-server":true,"enable-remote-auto-shutdown":true,"remote-auto-shutdown-without-delay":false,"use-host-proxy":false,"without-browser-env-var":false,"help":false,"version":false,"user-data-dir":"/home/codespace/.vscode-remote/data","builtin-extensions-dir":"/vscode/bin/linux-x64/2901c5ac6db8a986a5666c3af51ff804d05af0d4/extensions","extensions-dir":"/home/codespace/.vscode-remote/extensions","logsPath":"/home/codespace/.vscode-remote/data/logs/20250629T001733"}
2025-06-29 00:17:34.131 [info]




2025-06-29 00:17:34.131 [trace] [File Watcher (node.js)] Request to start watching: /home/codespace/.vscode-remote/data/Machine (excludes: <none>, includes: <all>, filter: <none>, correlationId: <none>),/home/codespace/.vscode-remote/data/Machine/settings.json (excludes: <none>, includes: <all>, filter: <none>, correlationId: <none>)
2025-06-29 00:17:34.131 [trace] [File Watcher (node.js)] Started watching: '/home/codespace/.vscode-remote/data/Machine'
2025-06-29 00:17:34.131 [trace] [File Watcher (node.js)] Started watching: '/home/codespace/.vscode-remote/data/Machine/settings.json'
2025-06-29 00:17:34.143 [trace] Installing builtin extensions passed via args...
2025-06-29 00:17:34.144 [trace] Started scanning system extensions
2025-06-29 00:17:34.145 [trace] Started scanning user extensions {"$mid":1,"external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"}
2025-06-29 00:17:34.149 [info] Extension host agent started.
2025-06-29 00:17:34.168 [trace] [File Watcher (node.js)] Request to start watching: /home/codespace/.vscode-remote/extensions (excludes: <none>, includes: <all>, filter: <none>, correlationId: <none>)
2025-06-29 00:17:34.169 [debug] Error while reading the extension cache file: /home/codespace/.vscode-remote/data/CachedProfilesData/__default__profile__/extensions.builtin.cache Unable to read file '/home/codespace/.vscode-remote/data/CachedProfilesData/__default__profile__/extensions.builtin.cache' (Error: Unable to resolve nonexistent file '/home/codespace/.vscode-remote/data/CachedProfilesData/__default__profile__/extensions.builtin.cache')
2025-06-29 00:17:34.171 [info] Started initializing default profile extensions in extensions installation folder. file:///home/codespace/.vscode-remote/extensions
2025-06-29 00:17:34.231 [trace] Deleting from cache /home/codespace/.vscode-remote/extensionsCache/esbenp.prettier-vscode-11.0.0
2025-06-29 00:17:34.231 [trace] Deleting from cache /home/codespace/.vscode-remote/extensionsCache/ms-toolsai.jupyter-2025.6.2025062701
2025-06-29 00:17:34.231 [trace] Deleting from cache /home/codespace/.vscode-remote/extensionsCache/ritwickdey.liveserver-5.7.9
2025-06-29 00:17:34.231 [trace] Deleting from cache /home/codespace/.vscode-remote/extensionsCache/vscjava.vscode-java-dependency-0.24.1
2025-06-29 00:17:34.239 [trace] [File Watcher (node.js)] Started watching: '/home/codespace/.vscode-remote/extensions'
2025-06-29 00:17:34.315 [info] ComputeTargetPlatform: linux-x64
2025-06-29 00:17:34.355 [trace] [File Watcher (node.js)] [raw] ["rename"] extensions.json
2025-06-29 00:17:34.356 [trace] [File Watcher (node.js)] [raw] ["change"] extensions.json
2025-06-29 00:17:34.356 [trace] [File Watcher (node.js)] [ADDED] /home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:34.359 [info] Completed initializing default profile extensions in extensions installation folder. file:///home/codespace/.vscode-remote/extensions
2025-06-29 00:17:34.360 [trace] Scanned user extensions: 0
2025-06-29 00:17:34.361 [trace] [File Watcher (node.js)] Request to start watching: /home/codespace/.vscode-remote/extensions/extensions.json (excludes: <none>, includes: <all>, filter: <none>, correlationId: <none>)
2025-06-29 00:17:34.363 [trace] [File Watcher (node.js)] Started watching: '/home/codespace/.vscode-remote/extensions/extensions.json'
2025-06-29 00:17:34.372 [trace] Scanned system extensions: 32
2025-06-29 00:17:34.383 [info] ComputeTargetPlatform: linux-x64
2025-06-29 00:17:34.433 [trace] [File Watcher (node.js)]  >> normalized [ADDED] /home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:34.455 [trace] [File Watcher (node.js)] [CHANGED] /home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:34.484 [trace] [127.0.0.1][ea5b98b1][ExtensionHostConnection] - startParams language: en
2025-06-29 00:17:34.484 [trace] [127.0.0.1][ea5b98b1][ExtensionHostConnection] - startParams env: {}
2025-06-29 00:17:34.485 [info] [127.0.0.1][ea5b98b1][ExtensionHostConnection] New connection established.
2025-06-29 00:17:34.487 [info] [127.0.0.1][02a87854][ManagementConnection] New connection established.
2025-06-29 00:17:34.488 [trace] resolveShellEnv(): skipped (--force-disable-user-env)
2025-06-29 00:17:34.495 [info] [127.0.0.1][ea5b98b1][ExtensionHostConnection] <2801> Launched Extension Host Process.
2025-06-29 00:17:34.530 [trace] [File Watcher (node.js)]  >> normalized [CHANGED] /home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:34.654 [trace] ExtensionManagementService.updateControlCache
2025-06-29 00:17:34.655 [trace] resolveShellEnv(): skipped (--force-disable-user-env)
2025-06-29 00:17:34.657 [trace] Started scanning system extensions
2025-06-29 00:17:34.660 [trace] Started scanning user extensions {"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"}
2025-06-29 00:17:34.662 [trace] Scanning extensions using UI language: en
2025-06-29 00:17:34.686 [info] Log level changed to info
2025-06-29 00:17:35.439 [info] Installing builtin extension 'github.github-vscode-theme'...
2025-06-29 00:17:35.446 [info] Installing builtin extension 'github.copilot-chat'...
2025-06-29 00:17:35.453 [info] Installing builtin extension 'github.vscode-pull-request-github'...
2025-06-29 00:17:35.454 [info] Installing builtin extension 'github.copilot'...
2025-06-29 00:17:35.475 [info] Installing builtin extension 'github.codespaces'...
2025-06-29 00:17:35.480 [info] Getting Manifest... github.github-vscode-theme
2025-06-29 00:17:35.481 [info] Getting Manifest... github.copilot-chat
2025-06-29 00:17:35.482 [info] Getting Manifest... github.vscode-pull-request-github
2025-06-29 00:17:35.482 [info] Getting Manifest... github.copilot
2025-06-29 00:17:35.482 [info] Getting Manifest... github.codespaces
2025-06-29 00:17:35.824 [info] Installing extension: github.copilot-chat {"isMachineScoped":true,"installPreReleaseVersion":false,"isBuiltin":true,"installGivenVersion":false,"isApplicationScoped":true,"profileLocation":{"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"},"productVersion":{"version":"1.101.2","date":"2025-06-24T20:27:15.391Z"}}
2025-06-29 00:17:35.826 [info] Installing extension: github.github-vscode-theme {"isMachineScoped":true,"installPreReleaseVersion":false,"isBuiltin":true,"installGivenVersion":false,"isApplicationScoped":true,"profileLocation":{"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"},"productVersion":{"version":"1.101.2","date":"2025-06-24T20:27:15.391Z"}}
2025-06-29 00:17:35.827 [info] Installing extension: github.copilot {"isMachineScoped":true,"installPreReleaseVersion":false,"isBuiltin":true,"installGivenVersion":false,"isApplicationScoped":true,"profileLocation":{"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"},"productVersion":{"version":"1.101.2","date":"2025-06-24T20:27:15.391Z"}}
2025-06-29 00:17:35.827 [info] Installing extension: github.vscode-pull-request-github {"isMachineScoped":true,"installPreReleaseVersion":false,"isBuiltin":true,"installGivenVersion":false,"isApplicationScoped":true,"profileLocation":{"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"},"productVersion":{"version":"1.101.2","date":"2025-06-24T20:27:15.391Z"}}
2025-06-29 00:17:35.828 [info] Installing extension: github.codespaces {"isMachineScoped":true,"installPreReleaseVersion":false,"isBuiltin":true,"installGivenVersion":false,"isApplicationScoped":true,"profileLocation":{"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"},"productVersion":{"version":"1.101.2","date":"2025-06-24T20:27:15.391Z"}}
2025-06-29 00:17:35.989 [info] Getting Manifest... github.copilot-chat
2025-06-29 00:17:37.273 [info] Getting Manifest... github.copilot
2025-06-29 00:17:42.966 [info] Extension signature verification result for github.copilot: Success. Internal Code: 0. Executed: true. Duration: 4884ms.
2025-06-29 00:17:43.084 [info] Extension signature verification result for github.vscode-pull-request-github: Success. Internal Code: 0. Executed: true. Duration: 4944ms.
2025-06-29 00:17:43.140 [info] Extension signature verification result for github.codespaces: Success. Internal Code: 0. Executed: true. Duration: 4973ms.
2025-06-29 00:17:43.189 [info] Extension signature verification result for github.github-vscode-theme: Success. Internal Code: 0. Executed: true. Duration: 5133ms.
2025-06-29 00:17:43.264 [info] Extension signature verification result for github.copilot-chat: Success. Internal Code: 0. Executed: true. Duration: 5146ms.
2025-06-29 00:17:43.302 [info] Extracted extension to file:///home/codespace/.vscode-remote/extensions/github.github-vscode-theme-6.3.5: github.github-vscode-theme
2025-06-29 00:17:43.320 [info] Renamed to /home/codespace/.vscode-remote/extensions/github.github-vscode-theme-6.3.5
2025-06-29 00:17:43.438 [info] Extracted extension to file:///home/codespace/.vscode-remote/extensions/github.vscode-pull-request-github-0.112.0: github.vscode-pull-request-github
2025-06-29 00:17:43.457 [info] Renamed to /home/codespace/.vscode-remote/extensions/github.vscode-pull-request-github-0.112.0
2025-06-29 00:17:43.671 [info] Extracted extension to file:///home/codespace/.vscode-remote/extensions/github.codespaces-1.17.3: github.codespaces
2025-06-29 00:17:43.685 [info] Renamed to /home/codespace/.vscode-remote/extensions/github.codespaces-1.17.3
2025-06-29 00:17:43.794 [info] Extracted extension to file:///home/codespace/.vscode-remote/extensions/github.copilot-chat-0.28.3: github.copilot-chat
2025-06-29 00:17:43.807 [info] Renamed to /home/codespace/.vscode-remote/extensions/github.copilot-chat-0.28.3
2025-06-29 00:17:43.983 [info] Extracted extension to file:///home/codespace/.vscode-remote/extensions/github.copilot-1.338.0: github.copilot
2025-06-29 00:17:43.992 [info] Renamed to /home/codespace/.vscode-remote/extensions/github.copilot-1.338.0
2025-06-29 00:17:44.002 [info] Extension installed successfully: github.github-vscode-theme file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:44.003 [info] Extension installed successfully: github.vscode-pull-request-github file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:44.003 [info] Extension installed successfully: github.codespaces file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:44.003 [info] Extension installed successfully: github.copilot-chat file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:44.003 [info] Extension installed successfully: github.copilot file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:17:44.010 [info] Extension 'github.github-vscode-theme' v6.3.5 was successfully installed.
2025-06-29 00:17:44.010 [info] Extension 'github.vscode-pull-request-github' v0.112.0 was successfully installed.
2025-06-29 00:17:44.010 [info] Extension 'github.codespaces' v1.17.3 was successfully installed.
2025-06-29 00:17:44.010 [info] Extension 'github.copilot-chat' v0.28.3 was successfully installed.
2025-06-29 00:17:44.010 [info] Extension 'github.copilot' v1.338.0 was successfully installed.
2025-06-29 00:21:02.328 [info] Getting Manifest... saikatdas.output-formatter
2025-06-29 00:21:02.359 [info] Installing extension: saikatdas.output-formatter {"isMachineScoped":false,"installPreReleaseVersion":false,"pinned":false,"isApplicationScoped":false,"profileLocation":{"$mid":1,"fsPath":"/home/codespace/.vscode-remote/extensions/extensions.json","external":"file:///home/codespace/.vscode-remote/extensions/extensions.json","path":"/home/codespace/.vscode-remote/extensions/extensions.json","scheme":"file"},"productVersion":{"version":"1.101.2","date":"2025-06-24T20:27:15.391Z"}}
2025-06-29 00:21:03.566 [info] Extension signature verification result for saikatdas.output-formatter: Success. Internal Code: 0. Executed: true. Duration: 874ms.
2025-06-29 00:21:03.590 [info] Extracted extension to file:///home/codespace/.vscode-remote/extensions/saikatdas.output-formatter-1.2.3: saikatdas.output-formatter
2025-06-29 00:21:03.597 [info] Renamed to /home/codespace/.vscode-remote/extensions/saikatdas.output-formatter-1.2.3
2025-06-29 00:21:03.608 [info] Extension installed successfully: saikatdas.output-formatter file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:21:06.564 [info] Uninstalling extension from the profile: saikatdas.output-formatter@1.2.3 file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:21:06.601 [info] Marked extension as removed saikatdas.output-formatter-1.2.3
2025-06-29 00:21:06.841 [info] Successfully uninstalled extension from the profile saikatdas.output-formatter@1.2.3 file:///home/codespace/.vscode-remote/extensions/extensions.json
2025-06-29 00:21:15.877 [info] [127.0.0.1][607bdb5e][ExtensionHostConnection] New connection established.
2025-06-29 00:21:15.881 [info] [127.0.0.1][607bdb5e][ExtensionHostConnection] <6404> Launched Extension Host Process.
2025-06-29 00:21:15.882 [info] [127.0.0.1][3377424d][ManagementConnection] New connection established.
2025-06-29 00:21:38.961 [info] [127.0.0.1][02a87854][ManagementConnection] The client has disconnected, will wait for reconnection 3h before disposing...
2025-06-29 00:22:34.150 [info] New EH opened, aborting shutdown
2025-06-29 00:23:11.580 [info] [127.0.0.1][02a87854][ManagementConnection] Another client has connected, will shorten the wait for reconnection 5m before disposing...
2025-06-29 00:23:11.580 [info] [127.0.0.1][455683f5][ManagementConnection] New connection established.
2025-06-29 00:23:11.630 [info] [127.0.0.1][2b4c94a5][ExtensionHostConnection] New connection established.
2025-06-29 00:23:11.637 [info] [127.0.0.1][2b4c94a5][ExtensionHostConnection] <8189> Launched Extension Host Process.
2025-06-29 00:23:34.336 [info] [127.0.0.1][3377424d][ManagementConnection] The client has disconnected, will wait for reconnection 3h before disposing...
2025-06-29 00:24:14.745 [info] [127.0.0.1][3377424d][ManagementConnection] Another client has connected, will shorten the wait for reconnection 5m before disposing...
2025-06-29 00:24:14.747 [info] [127.0.0.1][a81a2f3b][ExtensionHostConnection] New connection established.
2025-06-29 00:24:14.753 [info] [127.0.0.1][a81a2f3b][ExtensionHostConnection] <9731> Launched Extension Host Process.
2025-06-29 00:24:15.179 [info] [127.0.0.1][1b79aaf1][ManagementConnection] New connection established.
2025-06-29 00:24:22.524 [info] [127.0.0.1][7db97e5e][ManagementConnection] New connection established.
2025-06-29 00:24:22.549 [info] [127.0.0.1][e06554df][ExtensionHostConnection] New connection established.
2025-06-29 00:24:22.554 [info] [127.0.0.1][e06554df][ExtensionHostConnection] <10217> Launched Extension Host Process.
2025-06-29 00:24:46.362 [info] [127.0.0.1][1b79aaf1][ManagementConnection] The client has disconnected, will wait for reconnection 3h before disposing...
2025-06-29 00:24:46.777 [info] [127.0.0.1][1b79aaf1][ManagementConnection] Another client has connected, will shorten the wait for reconnection 5m before disposing...
2025-06-29 00:24:46.777 [info] [127.0.0.1][5b085fde][ManagementConnection] New connection established.
2025-06-29 00:24:46.797 [info] [127.0.0.1][66c3be0a][ExtensionHostConnection] New connection established.
2025-06-29 00:24:46.801 [info] [127.0.0.1][66c3be0a][ExtensionHostConnection] <11485> Launched Extension Host Process.
2025-06-29 00:25:09.823 [info] [127.0.0.1][7db97e5e][ManagementConnection] The client has disconnected, will wait for reconnection 3h before disposing...
2025-06-29 00:26:16.271 [info] [127.0.0.1][ea5b98b1][ExtensionHostConnection] <2801> Extension Host Process exited with code: 0, signal: null.
2025-06-29 00:28:11.722 [info] [127.0.0.1][02a87854][ManagementConnection] The reconnection short grace time of 5m has expired, so the connection will be disposed.
2025-06-29 00:28:11.866 [info] [127.0.0.1][607bdb5e][ExtensionHostConnection] <6404> Extension Host Process exited with code: 0, signal: null.
2025-06-29 00:29:14.885 [info] [127.0.0.1][3377424d][ManagementConnection] The reconnection short grace time of 5m has expired, so the connection will be disposed.
2025-06-29 00:29:22.638 [info] [127.0.0.1][a81a2f3b][ExtensionHostConnection] <9731> Extension Host Process exited with code: 0, signal: null.
2025-06-29 00:29:46.901 [info] [127.0.0.1][1b79aaf1][ManagementConnection] The reconnection short grace time of 5m has expired, so the connection will be disposed.
2025-06-29 00:29:47.260 [info] [127.0.0.1][e06554df][ExtensionHostConnection] <10217> Extension Host Process exited with code: 0, signal: null.
