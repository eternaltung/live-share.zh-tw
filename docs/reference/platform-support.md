---
title: 平台和語言支援-Visual Studio Live Share |Microsoft Docs
description: Visual Studio Live share 的平台和語言支援的概觀。
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
ms.openlocfilehash: 5c8429779bcfe39842ba298c3b6371daa1cf7fe4
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255545"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>語言和平台支援

Visual Studio Live Share 的功能被用來跨各種不同的環境的語言和應用程式平台運作。 不過，根據有大量的變化，某些平台和語言會比其他更完整。 本文件涵蓋目前已知的狀態數目的受歡迎的語言及平台目前支援的功能。

請參閱語言或平台，您需要嗎？ 想要新增一個您沒有看到嗎？ [在此投票。](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

所有語言 / 平台都有相同的檔案時的 intellisense (安裝個別的擴充功能），以及顏色標示和共同編輯支援。 以下涵蓋進階功能，目前不完整的通用支援清單中：

### <a name="languages"></a>語言

| 語言 | 共用的語言服務 | 共用偵錯 |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *N/A* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
| CSHTML | *N/A* <sup>1</sup> | ✅ |
| CSS | *N/A* | *N/A* |
| Dart | ✅ | ✅ |
| Docker | ✅ | *N/A* |
| 值藥劑 | ✅ | ✅ |
| Elm | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| 流程 | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *N/A* |
| 移至 | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
| GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *N/A* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *N/A* | *N/A* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *N/A* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Pascal 命名法 | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *N/A* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [Reason/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *N/A* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/A* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| 在 solidity | ✅ | *N/A* <sup>4</sup> |
| SQL / T-SQL | *N/A* | *N/A* <sup>4</sup> |
| [手寫筆](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/A* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup>中的無 CSHTML 支援C#延伸模組。<br />
<sup>2</sup>進行用戶端偵錯時，在 HTML 中內嵌的 JavaScript 的支援。<br />
<sup>3</sup> JavaScript / TypeScript 偵錯節點或瀏覽器。<br />
<sup>4</sup>各自適用於 VS Code 延伸模組目前不支援偵錯。 因為如此，我們將調查加入共同偵錯支援。 <br />

### <a name="platforms"></a>平台

| 應用程式/平台類型 | 共用偵錯 | 應用程式共用 |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/A* |
| Azure App Service | ✅ | *N/A* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure 函式 （本機和遠端） | ✅ | ✅ <sup>1</sup> |
| 區塊鏈 （以太坊） | ✅ | ✅ <sup>1</sup> |
| 主控台 / CLI | ✅ | ✅ <sup>4</sup> |
| 資料庫 | <sup>5</sup> | ✅ <sup>1</sup> |
| 桌面 （Electron/原生） | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| 遊戲 (Unity) | ✅ | <sup>9</sup> |
| 遊戲 (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes （YAML、 Helm） | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/A* | ✅ <sup>6</sup> |
| 行動裝置 (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| 行動裝置 （原生） | ✅ | <sup>9</sup> |
| 行動裝置 (React Native) | ✅ | ✅ <sup>1,8</sup> |
| Web 應用程式 / API （後端） | ✅ | ✅ <sup>1</sup> |
| Web 應用程式 （前端） | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| VS Code 擴充功能 | | <sup>9</sup> |

<sup>1</sup>經由[共用本機伺服器](../use/vscode.md#share-a-server)。<br />
<sup>2</sup>偵錯作業會針對主機的瀏覽器而非來賓。<br />
<sup>3</sup>共用後端。<br />
<sup>4</sup>支援透過共用的終端機。<br />
<sup>5</sup>偵錯資料庫預存程序目前不支援 <br />
<sup>6</sup>透過 「 預覽 」。 不過，由於已知問題仍未顯示影像。 [投票 (👍) 以下。](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> Cordova 應用程式可以透過 「 瀏覽器 」 平台共用<br />
<sup>8</sup> react Native 應用程式可以共用透過展覽並[共用伺服器](../use/vscode.md#share-a-server)。<br />
<sup>9</sup> live Share 目前不支援共用的 windows 螢幕。 [投票 (👍) 以下。](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

雖然大部分語言都有某些單一檔案 Intellisense 支援，但也有下面所述的一些注意事項。 所有語言/平台都支援共同編輯。 清單的其餘部分涵蓋進階的功能，目前不完整的通用支援：

### <a name="languages"></a>語言

| 語言 | 單一檔案的語言服務 | 整個專案的語言服務 | 同時偵錯 |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/A* | <sup>2</sup> |
| CSS | ✅ | *N/A* | *N/A* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *N/A* | *N/A* |
| PowerShell | ✅ | *N/A* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/A* | <sup>4</sup> |
| SQL / T-SQL | ✅ | *N/A* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/A* | ✅ |

<sup>1</sup>間距：CSHTML、 VBHTML 和 ASPX 有已知問題大約內嵌C#指定程式碼後置的 /VB 支援C#/VB 檔案就不會因為未實作的完整 intellisense 的方式解析。 [投票 (👍) CSHTML/VBHTML 在這裡。](https://github.com/MicrosoftDocs/live-share/issues/59) [投票 (👍) ASPX 在這裡。](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup>進行用戶端偵錯時，在 HTML 中內嵌的 JavaScript 的支援。<br />
<sup>3</sup> JavaScript / TypeScript 偵錯節點或瀏覽器。<br />
<sup>4</sup>雖然偵錯 XAML 本身就技術上而言不適用，則支援偵錯程式碼後置。<br />
<sup>5</sup>間距：R 語言的一端客體上聯結，並在每個新行字元之後的服務錯誤。 不支援。 [投票 (👍) 以下。](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>平台

| 應用程式/平台類型 | 共同偵錯 | 應用程式共用 |
|-------------------|--------------|-------------|
| Web 應用程式 / API （後端） | ✅ | ✅ <sup>1</sup> |
| Web 應用程式 （前端） | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| 資料庫 | <sup>4</sup> | ✅ <sup>5</sup> |
| 主控台 / CLI | ✅ | ✅ <sup>6</sup> |
| 桌面 (WinForms) | ✅ | |
| 桌面 (WPF) | ✅ | |
| 通用 Windows 平台 | ✅ |  |
| VS 擴充功能 | ✅ |  |

<sup>1</sup>經由[共用本機伺服器](../use/vs.md#share-a-server)。 ASP.NET Web 應用程式也可以使用[自動的 web 應用程式共用](../use/vs.md#automatic-web-app-sharing)。<br />
<sup>2</sup>偵錯作業會針對主機的瀏覽器而非來賓。<br />
<sup>3</sup>共用後端。<br />
<sup>4</sup>偵錯資料庫預存程序目前不支援 <br />
<sup>5</sup>經由[共用本機伺服器](../use/vs.md#share-a-server)。 <br />
<sup>6</sup>部分支援透過共用的終端機。<br />
<sup>?</sup> 尚未驗證過。

## <a name="see-also"></a>另請參閱

- [延伸模組支援](extensions.md)
- [Live Share 的連線需求](connectivity.md)
- [Live Share 的安全性功能](security.md)
- [所有主要 bug、 功能要求和限制](https://aka.ms/vsls-issues)
- [所有的功能要求和限制](https://aka.ms/vsls-feature-requests)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
