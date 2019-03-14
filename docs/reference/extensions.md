---
title: 擴充功能和生態系統支援-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live share 的延伸模組支援的概觀。
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5a9787643643c22ca7302528dc794480d09df902
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255590"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>擴充功能和生態系統支援

其中一個主要目標的 Visual Studio Live Share 可讓開發人員彼此共同作業的最愛，並[**高度自訂化**](https://marketplace.visualstudio.com/)工具。 如此一來，臨機操作互動就會經常發生，同時保有以視覺化方式熟悉且工學，無論什麼您就可協助使用。 若要這麼做，請務必在共同作業工作階段中的參與者都能夠繼續使用支援的任何延伸模組及其[個人喜好設定和工作流程](#user-specific-extensions)（例如/圖示的色彩佈景主題、 按鍵繫結關係、 編輯器產能增強工具）。

此外，要加入為共同作業工作階段的動作立即越好，同時保有高生產力的 Visual Studio Live Share 目標是啟用自動運用具有共用其主應用程式的專案特定工具的來賓。 如此一來，您可以直接按一下連結，啟動您選擇的工具並開始進行共同作業，而不需要任何額外的設定。 為了達到此目的，該延伸模組的電源核心[編輯、 建置和偵錯工作流程](#project-specific-extensions)、 無障礙地 「 遠端 」 從主機到客體，以便一些事，像是自動完成，請移至定義，以及偵錯 」只要工作 」。

本文件涵蓋目前的已知狀態 vast 的擴充功能生態系統，以及 「 計分卡 」 的上述目標。 如果您遇到不符合此準則，並務必使用您個人的工作流程延伸模組，然後請[告訴我們 ！](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>使用者專屬的延伸模組

支援使用者特定的自訂延伸模組**必須**主機的工作並**應該**工作的所有來賓。 如果主控件中，擴充功能無法正常運作，就是迴歸，，可能是 bug，以在 Visual Studio Live Share (請[提出問題](https://github.com/MicrosoftDocs/live-share/issues/new)如果您會看到一個 ！)。 如果延伸模組不會如預期般的來賓，它可能需要[延伸模組本身中的變更](#known-issues)，和我們將使用以位址/改善這些案例的生態系統。

### <a name="visual-studio-code"></a>Visual Studio Code

| 分類 | 個範例 | 客體支援？ | 共同作業？ |
|-|-|-|-|
| 色彩佈景主題 | [一個深色 Pro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme)，[輸出色彩標示器](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer)，[彩虹字串](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string)，[彩色區域](https://github.com/jmihelcic/colored-regions)，[縮排區塊反白顯示](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting)， [Todo 反白顯示](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)，[括號配對色彩標示器](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *N/A* |
| 圖示集 | [vscode 圖示](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons)， [Visual Studio 傳統圖示](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *N/A* |
| 按鍵繫結 | [Vim](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim)， [IntelliJ IDEA 按鍵繫結關係](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings)， [Emacs 易記快速鍵](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *N/A* |
| 程式碼片段 | [Angular v5 程式碼片段](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2)， [HTML 程式碼片段](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets)， [SVG 圖示](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons)，[檔案標頭](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *N/A* <sup>1</sup> |
| 組織 | [設定同步處理](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)，[專案經理](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager)， [Timeit](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit)，[檢查點](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints)， [TODO 剖析器](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser)，[我的最愛](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) （❌），[書籤](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks)（❌） | ✅ <sup>2</sup> | *N/A* <sup>3</sup> |
| 產能 | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)，[自動重新命名標記](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)，[程式碼大綱](https://github.com/patrys/vscode-code-outline)，[色彩反白顯示](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight)，[遞增選取](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection)， [Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer)，[影像預覽](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview)， [JSON 協助程式](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper)（暫留）[色彩選擇器](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color)，[資料指標中複製 Word](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word)，[CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens)、 [Git 共同作者](https://github.com/rjimenezda/vscode-coauthor)， [JavaScript Booster](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions，)[渦輪主控台記錄檔](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log)， [移至下一個/上一個成員](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member)，[自動捲動](https://github.com/PejmanNik/vscode-autoScroll?files=1)， [NPM 匯入版本](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version)（❌），[匯入成本](https://github.com/wix/import-cost)（❌） | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| Repl | [REST 用戶端](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)，[程式碼執行器](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)， [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode)， [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| 資源管理員 | [mssql](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql)， [ftp 簡單](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple)， [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)， [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker)， [Brew 服務](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *除非使用者已熟悉的程式碼片段，它們不能期望它可供使用，因此，讓它們共用一定就毫無意義。*

<sup>2</sup> *這些延伸模組類別很因此不同，它們全部，就無法假設使用。不過，理論上，也應該如此，而我們會將追蹤的索引鍵未。*

<sup>3</sup> *這些延伸模組類別可能會受益於共同作業體驗，並因此我們需要知道使用者意見反應 ！*

<sup>4</sup> *這些都需要已安裝執行階段工具 (例如 Node.js)，並在本機執行程式碼來處理客體。*

<sup>5</sup> *這些運作方式是連接到伺服器的某種，以及使用它的其中一個集中式伺服器客體已共用的伺服器。*

### <a name="visual-studio"></a>Visual Studio

即將推出。

## <a name="project-specific-extensions"></a>專案專屬的延伸模組

主應用程式安裝延伸模組，可支援核心編輯、 建置和偵錯的應用程式，專為語言/平台/程式庫/sdk，應該會自動提供給來賓，而不需要安裝任何項目。 如此一來，主機可以設定其環境，以支援提高生產力的開發專案的資料，並允許其立即加入它們，而不需要的其他先決條件的來賓。 專案專屬的延伸模組不是主觀或個人以任何方式，因為它們可以決定性地共用從主應用程式-來賓，而不會影響任何人熟悉的環境。

此外，為了支援專案專屬的延伸模組已安裝的來賓，但主機未，他們可在理想情況下提供降級的功能尚未體驗 （例如取得單一檔案 intellisense，能夠格式化文件）。

| 分類 | 個範例 | 共用嗎？ | 客體支援？ |
|-------|----------|--------|-----|
| 文法 / 語法反白顯示 | [擷取殼層](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish)， [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx)， [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur)， [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv)， [ES6 字串 HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html)， [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus)，[彩虹 CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| 語言服務 | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)，[路徑 Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense)， [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| JSON 結構描述 | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| Linter | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)， [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)，[拼字檢查工具的程式碼](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)， [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| 格式器 | [美化](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)，[美化](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| 偵錯工具 | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python)， [Chrome 偵錯工具](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| 測試執行器 | [Java 測試執行器](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test)， [Mocha 提要欄位](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar)， [Postman 執行器](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman)， [Jest 執行器](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner)，[海王星](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| 自訂檔案預覽程式 | [SVG 預覽](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer)， [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz)， [Markdown 映像大小](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| 檔案/專案產生器 | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions)， [C/c + + 專案產生器](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| 原始檔控制提供者 | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm)， [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *目前只支援C#和 JavaScript/TypeScript，即將推出更多的支援。*

<sup>2</sup> *因為來賓無法存取本機檔案，則只會支援目前現用文件。*

<sup>3</sup> *共用核心偵錯體驗，不過，不會自動轉送任何啟動的伺服器。*

<sup>4</sup> *來賓沒有應用程式中的本機副本，因此，執行的應用程式和任何偵錯工作階段需要主機的電腦上啟動。*

<sup>5</sup> *，任何產生的終端機、 輸出窗格和錯誤已同時共用來賓需要執行測試的輸出。*

<sup>6</sup> *幾乎所有的這些會使用 Node.js`fs`模組直接建立檔案，不會運作。*

### <a name="visual-studio"></a>Visual Studio

即將推出。

## <a name="known-issues"></a>已知問題

目前已知的延伸模組的問題，可能使他們無法從來賓 （以及其因應措施），共同作業工作階段的內容中的工作，因此，可能會影響其工作流程如下：

### <a name="visual-studio-code"></a>Visual Studio Code

| 問題 | 原因 | 因應措施 |
|-|-|-|
| 使用 Node.js`fs`模組來偵測/讀取檔案 （例如組態檔中），或列舉目錄 （以及不是語言服務）。 | 來賓無法存取本機檔案。 | 1.依正常程序會降低使用者體驗 *（如果可能）。*<br /><br />2.使用`openTextDocument`和`findFiles`工作區 Api 來讀取並列舉檔案。 |
| 使用 Node.js`fs`模組來建立或寫入檔案 | *同上* | *N/A*您可以使用`openTextDocument(Uri)`API，以建立`untitled`檔案，但您無法將它儲存至檔案系統中，在特定路徑直接。 |
| 根據專案隨附的文件庫或工具 | *同上* | 1.套件組合後援的擴充功能的相依性版本<br><br> 2.支援全域安裝，以解除封鎖來賓，如果他們願意明確地加以安裝。<br><br> 3.遠端狀態/動作如果可能，因為主應用程式都有正確的相依性。 |
| 使用 Node.js`fs`模組來建立目錄 | *同上* | *N/A* |
| 限制功能文件使用`file`配置。 | 在客體的側邊使用檔案`vsls`配置。 | 新增支援`vsls`文件 ([範例](https://github.com/CoenraadS/BracketPair/pull/73)) |
| 使用`Uri.file`方法和 （或) `Uri.fsPath` / `TextDocument.fileName`序列化/剖析 Uri 的成員 | *同上* | 使用`Uri.parse`並`Url.toString()`相反地，其中維護，並採用檔案配置 ([範例](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| 使用`workspace.openTextDocument`方法而不是檔案路徑 `Uri` | *同上* | 提供`Uri`執行個體，而非原始檔案路徑字串 ([範例](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| 使用`workspace.rootPath`偵測工作區是否存在的屬性 | `workspace.rootPath`屬性呼叫`Uri.fsPath`第一天`workspaceFolder`在`workspace`，其中包含上述相同的問題 | 使用`workspace.workspaceFolders`屬性設為相反地，偵測是否有工作區，並如有需要看看每`workspaceFolder`的`Uri.scheme`來判斷它是否在本機或不 |
| 註冊語言服務時，未指定的文件結構描述 (透過`LanguageClient`，或`languages.register*`方法) | 來賓接收來自其本機的延伸模組，與主機的語言服務的結果，並因此，如果這兩個參與者都必須安裝相同語言服務延伸模組，來賓會看到的某些項目 （例如自動完成、 程式碼的重複項目動作） | 語言服務限制為僅限`file`並`untitled`配置 ([範例](https://github.com/vuejs/vetur/pull/756/files)) |
| 未核取的文件`Uri.scheme`之前填入`DiagnosticCollection`， | *同上* | 只會產生`Diagnostics`for`documents`其`Uri.scheme`  ===  `file` ([範例](https://github.com/Huachao/vscode-restclient/pull/196)) |
| 傳回時，不檢查工作區中配置`Tasks`來自自訂 `TaskProvider`  | 來賓顯示所有的遠端和本機工作，因此，會顯示重複的項目如果兩個參與者有相同的擴充功能安裝  | 只會傳回`Tasks`for `WorkspaceFolder`s 其`Uri.scheme`  ===  `file` ([範例](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Visual Studio

即將推出。

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>另請參閱

- [語言和平台支援](platform-support.md)
- [Live Share 的連線需求](connectivity.md)
- [Live Share 的安全性功能](security.md)
- [所有主要 bug、 功能要求和限制](https://aka.ms/vsls-issues)
- [所有的功能要求和限制](https://aka.ms/vsls-feature-requests)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
