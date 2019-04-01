---
title: 概觀 - Visual Studio Live Share | Microsoft Docs
description: Visual Studio Live Share 及其功能概觀。
ms.custom: null
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
  - liveshare
---

<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>什麼是 Visual Studio Live Share？

> **注意：Visual Studio Live Share 目前為預覽狀態。使用者體驗和功能不是最終版本。**

歡迎使用 Visual Studio Live Share！ Live Share 可讓您即時與其他人以共同作業方式編輯和偵錯，不論您所使用程式設計語言或建置的應用程式類型為何。 它可讓您立即且安全地共用您目前的專案，然後視需要共用偵錯工作階段、終端機執行個體、localhost Web 應用程式、語音通話等！

此外，不同於傳統的結對程式設計，Visual Studio Live Share 可讓開發人員共同作業，同時保留其個人編輯器喜好設定 (例如佈景主題、按鍵繫結關係)，以及擁有自己的資料指標。 這可讓您順暢地轉換對彼此的關注，並且能夠自行探索想法/工作。 在實務上，共同「和」獨立作業的這項能力提供對許多常見使用案例可能更自然的共同作業體驗。

準備好開始著手了嗎？ 在本文中，我們將帶您瀏覽一些概念，並說明如何安裝所需的延伸模組。 如需節錄版本，請參閱[共用](quickstart/share.md)和[加入](quickstart/join.md)快速入門。

> [!TIP]
> 您知道您可以「加入自己的共同作業工作階段」嗎？ 這讓您可以自行試用 Live Share，或是啟動 Visual Studio 或 VS Code 的執行個體，並從遠端連線到該執行個體！ 您甚至可以在這兩個執行個體上使用相同的身分識別。 趕緊去瞧一瞧！

## <a name="install-visual-studio-live-share"></a>安裝 Visual Studio Live Share

開始之前，您必須確定已安裝符合 Live Share 核心需求的 Visual Studio 或 Visual Studio Code 版本。

- **Visual Studio Code 1.22.0 (含) 以上版本** - Windows 7、8.1 或 10、macOS (僅限 Sierra 10.12 和以上版本)、64 位元 Linux (建議使用 64 位元 Ubuntu Desktop 16.04+、Fedora 27+) - [查看詳細資料](use/vscode.md#installation))。
- **Visual Studio 2017 15.6 (含) 以上版本** (任何版本) - Windows 7、8.1 或 10。
- **Visual Studio 2019** (任何版本) - Windows 7、8.1 或 10。

之後就能輕鬆下載並安裝 Visual Studio Live Share 延伸模組：

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. 安裝適用於 Windows (7、8.1 或 10)、macOS <b>(Sierra+)</b>、64 位元 Linux <b>的 <a href="https://code.visualstudio.com/">Visual Studio Code</a> (<a href="use/vscode.md#installation">詳細資料</a>)</b><br />
        2. 從 Marketplace 下載並安裝 Visual Studio Live Share 延伸模組。 <br />
        3. 重新載入並等候相依性下載和安裝 (查看狀態列)。<br />
        4. <strong>Linux</strong>：如果系統提示<a href="reference/linux.md#install-linux-prerequisites">安裝程式庫</a>，請按一下 [安裝]、輸入密碼，並在完成時重新啟動 VS Code。<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 (含) 以上版本</strong><br />
        1. 在 Windows (7、8.1 或 10) 上安裝最新版本的 <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6+)。<br/>
        2. 安裝<a href="reference/platform-support.md">支援的工作負載</a> (例如 ASP.NET、.NET Core、C++ 及/或 Node.js)。<br />
        3. 從 Marketplace 下載並安裝 Visual Studio Live Share 延伸模組。 <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. 安裝 <a href="https://aka.ms/vs-preview">Visual Studio 2019</a> 的最新預覽版本。<br/>
        2. 安裝<a href="reference/platform-support.md">支援的工作負載</a> (例如 ASP.NET、.NET Core、C++ 及/或 Node.js)。<br />
        3. Visual Studio Live Share 預設已安裝這些工作負載。 <br />
    </td>
</tr>
</table>

下載並使用 Visual Studio Live Share 即表示您同意[授權條款](https://aka.ms/vsls-license)和[隱私權聲明](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx)。 如果您遇到問題，請參閱[疑難排解](troubleshooting.md)。

這樣就全部完成了！ 您應該會在 VS Code 左下方的狀態列中看到一個符號，並在 Visual Studio 右上方看到一個 [共用] 按鈕。 請參閱文件的其餘部分以了解後續步驟！

## <a name="concepts-and-features"></a>概念和功能

如同任何產品，Visual Studio Live Share 提供以某些核心概念為建置基礎的一組強大功能。 本節提供您一些概念和簡短的功能導覽。

### <a name="collaboration-sessions"></a>共同作業工作階段

Visual Studio Live Share 中的所有共同作業活動都牽涉到單一**共同作業工作階段主持人**和一或多個**來賓**。 主持人是啟動共同作業工作階段的人員，而來賓是加入的任何人。

共同作業工作階段主持人可以使用其所有工具和服務，但來賓只能存取主持人與其共用的特定項目。 這包括程式碼、正在執行的伺服器、偵錯工作階段、終端機等。 目前所有共用內容都會保留在主持人的電腦上，而不會同步到雲端，或啟用「立即存取」並「已提高安全性」的來賓電腦。 優點是當來賓加入時，可以使用整個解決方案，而當主持人結束共同作業工作階段時，則無法再使用內容。 此外，IDE/編輯器為改善來賓效能所建立的暫存檔案會在工作階段結束時自動清除。

#### <a name="sharing"></a>共用

當您以主持人身分「共用」時，您會啟動共用專案、方案或資料夾內容的共同作業工作階段。 來賓可以使用您傳送給他們的邀請連結來存取此內容。 「共用」是「共用專案」的省略，它也開啟了共用其他功能 (例如偵錯) 的大門。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-project) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-project)

#### <a name="joining"></a>聯結

按一下主持人傳送給您的邀請連結，可讓您以來賓身分「加入」共同作業工作階段，並存取主持人選擇與您共用的任何內容或功能。 如果您已安裝延伸模組，網頁連結可讓您快速跳入共同作業工作階段；如果尚未安裝，網頁連結可讓您快速設定資訊。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#join-a-collaboration-session) [![VS](media/vs-icon-15x15.png)](use/vs.md#join-a-collaboration-session)

### <a name="features"></a>功能

#### <a name="co-editing"></a>共同編輯

當您以另一位共同作業者身分開啟相同的檔案時，您立即就能以「共同作業方式編輯」或「共同編輯」檔案的內容。 您可以查看每位共同作業者的編輯內容、其資料指標和選取項目等。 更棒的是，您不會被迫一直編輯相同的檔案，因此您可以適時共同作業並適當地採取個別行動。

> [!NOTE]
> 共同編輯有幾項限制。 如需依語言列出功能的狀態，請參閱[平台支援](reference/platform-support.md)。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-editing) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>關注和聚焦

您有時需要說明橫跨多個檔案或程式碼中多個位置的問題和設計。 在此情況下，在共同編輯時暫時關注同事的專案進度可能會很有用。 因此，身為來賓，當您加入共同作業工作階段時，您會自動「關注」主持人的編輯位置。 主持人和來賓只要按一下滑鼠，即可跳入和跳出對彼此的關注。 此外，您可能會發現想要求所有參與者都能關注您。 Live Share 可讓您要求所有人都將其注意力「聚焦」於您，並發出通知讓他們輕鬆回頭關注您。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#following) [![VS](media/vs-icon-15x15.png)](use/vs.md#following)

#### <a name="co-debugging"></a>共同偵錯

當您想要對困難的編碼問題或錯誤進行偵錯時，有額外的一雙眼會非常有用。 身為主持人，Live Share 會透過與所有來賓共用偵錯工作階段，來自動啟用「共同作業方式偵錯」或「共同偵錯」。 您與來賓都會取得共同編輯功能，並有能力在逐步共同作業時進行個別調查。

> [!NOTE]
> 如需依語言或平台列出偵錯功能的狀態，請參閱[平台支援](reference/platform-support.md)。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-debugging) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>共用伺服器/共用連接埠

共同偵錯時，能夠存取主持人針對偵錯工作階段所提供的不同應用程式連接埠會非常有用。 您可能想要在瀏覽器中存取應用程式、存取本機資料庫，或從您的工具叫用 REST 端點。 Live Share 可讓您「共用伺服器」，這會將主持人電腦上本機連接埠對應至每個來賓電腦上完全相同的連接埠。 身為來賓，您接著可以與應用程式互動，如同在電腦本機執行一樣 (例如主持人和來賓都能存取 http://localhost:3000) 上執行的 Web 應用程式)。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-server) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-server)

#### <a name="share-terminals"></a>共用終端機

新式開發經常會運用各種命令列工具。 幸運的是，Live Share 可讓身為主持人的您選擇與來賓「共用終端機」。 共用的終端機可以是唯讀或完全共同作業，因此您和您的來賓都能執行命令並看到結果。 身為主持人，您一律可以掌控並決定其他共同作業者是否能自行執行命令，還是只會看到命令輸出。 事實上，您想要保留給自己的任何項目，都能在未共用的終端機中執行。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-terminal) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>存取控制

Visual Studio Live Share 提供參與者一些不錯的共同作業方式。 不過，透過一些選項和彈性，來賓就可以與主持人互動，您可能想要明確核准來賓對特定檔案或資料夾進行加入或鎖定存取。 Live Share 有一些可協助您的設定，包括唯讀和要求接受來賓。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](reference/security.md) [![VS](media/vs-icon-15x15.png)](reference/security.md)

#### <a name="flexible-connection-modes"></a>彈性的連線模式

為達最佳效能，Visual Studio Live Share 支援兩種核心「連線模式」：「直接」和「轉送」。 在直接模式中，來賓會直接連線到主持人，而不需要經過網路。 轉送模式可讓位於完全不同網路的來賓透過多人線上交談系統連線到主持人。 在所有情況下，連線會經 SSH 或 SSL 加密，以確保只有共同作業者可透過網路掌握狀況。 根據預設，Live Share 處於「自動」模式，會先嘗試直接連線，再容錯移轉到轉送；但如果需要，您可以鎖定為單一模式。

**深入了解：**[![VS Code](media/vscode-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode) [![VS](media/vs-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode)

## <a name="see-also"></a>另請參閱

快速入門

- [共用您的第一個專案](quickstart/share.md)
- [加入您的第一個工作階段](quickstart/join.md)

做法

- [使用 Visual Studio Code 共同作業](use/vscode.md)
- [使用 Visual Studio 共同作業](use/vs.md)

參考資料

- [Live Share 的連線需求](reference/connectivity.md)
- [Live Share 的安全性功能](reference/security.md)
- [語言和平台支援](reference/platform-support.md)
- [延伸模組支援](reference/extensions.md)
- [版本資訊](https://aka.ms/vsls-releases)

有問題嗎？ 請參閱[疑難排解](troubleshooting.md)或[提供意見反應](support.md)。
