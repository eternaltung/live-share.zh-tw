---
title: Linux 安裝詳細資料-Visual Studio Live Share |Microsoft Docs
description: 在 Linux 上安裝 Visual Studio Live Share 的詳細的資訊。
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 013eb234e5acca02a39e90f0697a146039bb2a89
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255538"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Linux 安裝詳細資料

Linux 是變化極大的環境，而且可以複雜而難以取得使用與大量的桌面環境，以及散發套件。 如果您決定要支援的版本**Ubuntu 桌面**（16.04 +，） **CentOS 7**，或**Fedora 工作站**（27 以上），而且只用**VS 的官方發行版程式碼**，您應該會發現簡單的程序。 但是，您會使用非標準組態或下游的通訊群組，可能會或可能不會遇到一些營運。 本文件提供一些資訊需求以及一些疑難排解的詳細資料，有助於您啟動並執行，即使您的組態是唯一的社群支援。 請注意，僅支援 Live Share **64 位元 Linux**。

## <a name="install-linux-prerequisites"></a>安裝 Linux 必要條件

某些 Linux 版本遺漏 Live Share 需要運作的程式庫。 根據預設，Live Share 會嘗試偵測並安裝您的 Linux 必要條件。 Live Share 遇到的問題，可以源自遺漏要求您安裝它們的權限的程式庫時，您會看到快顯通知。

![Linux 必要條件會遺失快顯通知顯示訊息](../media/vscode-linux-prereq-missing.png)

當您按一下 「 安裝 」 時，終端機視窗會出現，您的作業系統將會要求您輸入您的系統管理員 / 根目錄 (sudo) 密碼，以繼續。 假設指令碼順利完成，重新載入 Visual Studio Code，當系統提示您時，應該會完成所有設定 ！ 您也可以查看**[因發行版本的祕訣](#tips-by-distribution)** 其他提示和因應措施如果有的話。

如果您看到訊息，指出指令碼不支援您的散發套件，請參閱 < **[社群支援的散發套件的秘訣](#tips-for-unsupported-distros)** 社群共用與我們的資訊。

如果您**不想為您執行命令的 VS Code**，您也可以選擇重新執行此指令碼的最新版本隨時以手動方式在終端機視窗中使用下列命令：

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>所發佈的秘訣

必要條件安裝指令碼上述涵蓋各種不同的散發套件，您可能想知道遺漏的項目通常從普通的安裝。 下列清單顯示在指定的散發套件的全新安裝中遺漏了關鍵的程式庫。 清單也會提供一些秘訣可協助您立即上手開始執行如果您遇到問題。

| 散發 | Vanilla 安裝遺漏的程式庫 | 額外的步驟 |
|--------|-------------------|----|
| Ubuntu 桌面 18.04 （64 位元） | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu 桌面 16.04 （64 位元） | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 （64 位元） | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 （64 位元） | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 （64 位元） |&lt;none&gt;  | <ul><li>確保 「 啟動 GNOME 服務在啟動 「 簽入 「 工作階段並啟動 」 的 [進階] 索引標籤。</li><li>如果您遇到登入問題時，安裝`seahorse`，啟動 [密碼和金鑰]，確認您有 「 登入 」 keyring，而且您可以解除鎖定。</li></ul> |
| Xubuntu 16.04 （64 位元） | &lt;none&gt; | <ul><li>確保 「 啟動 GNOME 服務在啟動 「 簽入 「 工作階段並啟動 」 的 [進階] 索引標籤。</li><li>如果您遇到登入問題時，安裝`seahorse`，啟動 [密碼和金鑰]，確認您有 「 登入 」 keyring，而且您可以解除鎖定。</li></ul> |
| Mint 19 肉桂 （64 位元） | &lt;none&gt;  | &lt;none&gt; |
| 仿造 18.3 肉桂 （64 位元） | &lt;none&gt;  | &lt;none&gt; |
| Debian 10 (Buster) 測試 （64 位元） | 不穩定，因此無法辨識的版本。 | <ul><li>Debian 測試和 Unstable (Sid) 未正式支援。</li><li>沒有[已知問題](https://github.com/dotnet/corefx/issues/33179)會影響 Live Share 的.NET Core 中。 </li><li>請參閱[這裡的因應措施](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249)。</li></ul> |
| Debian 9 GNOME 桌面 （64 位元） | &lt;none&gt; | <ul><li>您可能需要安裝`sudo`並將您的使用者新增至要使用自動的安裝指令碼的 sudo 群組。</li>  |
| Fedora 工作站 29 （64 位元） | `openssl-compat10` | &lt;none&gt; |
| Fedora 工作站 28 （64 位元） | &lt;none&gt; | &lt;none&gt; |
| Fedora 工作站 27 （64 位元） | &lt;none&gt; | &lt;none&gt; |
| CentOS 7 GNOME 桌面 （64 位元） | &lt;none&gt; | &lt;none&gt; |

請參閱**[社群支援的散發套件的秘訣](#tips-for-community-supported-distros)** 如需其他非 Debian / Ubuntu 或 RHL 架構的散發套件。

您也可以找到其他詳細資料[以下](#detailed-library-requirements)Live Share 需要之特定程式庫。

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>社群支援散發版本的祕訣

Debian 之外的散發套件 / Ubuntu 或 RHL 樹狀結構未正式支援 Visual Studio Code 或.NET Core。 因此，由延伸模組，它們是不正式支援 Visual Studio Live Share 是。 不過，社群提供 Live Share 啟動並執行多個其他散發套件的一些實用資訊。

> **歡迎使用的提取要求：** 如果您想要使用您最愛的散發套件更新這項資訊，請提交提取要求[此檔案](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md)docs GitHub 存放庫中。 更棒的是，如果您想要取得支援您最愛的散發套件的相依性安裝程式，您可以提交 PR[此檔案](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh)。

| 散發 | 工作嗎？ | Vanilla 安裝遺漏的程式庫 | 額外的步驟 |
|--------------|----------|-------------------|------------------|
| Arch Linux （64 位元） | 是 | 而異。 可能的程式庫： `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>受到[必要條件的安裝指令碼](#install-linux-prerequisites)。</li><li>使用[visual studio 程式碼-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR 套件適用於 VS Code。</li><li>`sudo` 將需要安裝到使用自動化的必要條件安裝指令碼。</li><li>`gnome-keyring` 可能需要額外[設定步驟](https://wiki.archlinux.org/index.php/GNOME/Keyring)一些桌面環境中。</ul> |
| Manjaro 17.1 （64 位元） | 是 | `xorg-xprop liburcu` | <ul><li>受到[必要條件的安裝指令碼](#install-linux-prerequisites)。</li><li>使用[visual studio 程式碼-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) AUR 套件適用於 VS Code。</li></ul> |
| openSuSE LEAP 15 KDE （64 位元） | 是 | `libopenssl1_0_0 gnome-keyring` | <ul><li>支援必要條件的安裝指令碼。</li></ul> |
| 索勒斯 3 （64 位元） | 是 | `xprop` | <ul><li>受到[必要條件的安裝指令碼](#install-linux-prerequisites)。</li><li>新版`vscode`版本 57 之前的封裝遺漏必要的 product.json 值 ([如下所示](#vs-code-oss-issues))。 升級`vscode`套件以解決此問題。</li></ul> |
| Gentoo （64 位元） | 是 | 具有高變動性。 可能遺漏的套件： `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>`visual-studio-code`封裝中**jorgicio**已知可用於覆疊。</li></ul>

## <a name="install-prerequisites-manually"></a>手動安裝先決條件

 雖然建議使用 Live Share**相依性安裝指令碼**，本節提供進一步的詳細資料程式庫需求萬一您想要自行執行這些步驟，或使用不支援的散發套件指令碼。

一般遺漏的文件庫中開啟了香草安裝可在[所發佈的祕訣](#tips-by-distribution)並[社群支援的散發套件的秘訣](#tips-for-unsupported-distros)區段。

### <a name="detailed-library-requirements"></a>詳細文件庫的需求

Visual Studio Live Share 的原生程式庫需求是來自其使用的.NET Core 2.1 中 libsecret 保存認證，以及其瀏覽器整合。 下表摘要說明這些需求正式支援.NET core 散發套件。

| 散發 | .NET core 所 | 認證儲存體需求| 瀏覽器整合需求 |
|--------------|-----------|--------------------|------------|
| Ubuntu 和下游的散發套件 | `libssl1.0.0 libkrb5-3 zlib1g libicu55` （在 Ubuntu 16.04，仿造 18.3） 或`libicu57`（適用於 Ubuntu 17.10) 或`libicu60`（Ubuntu 18.04 仿造 19） | `libsecret-1-0 gnome-keyring` （或 libsecret 支援 keyring-Kwallet nepodporuje libsecret） | `desktop-file-utils x11-utils` |
| Debian 9 和下游的散發套件 | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` （或 libsecret 支援 keyring-Kwallet nepodporuje libsecret） | `desktop-file-utils x11-utils` |
| RHL / CentOS / Fedora | `openssl-libs krb5-libs zlib libicu` Fedora 也需要 `compat-openssl10`| `libsecret gnome-keyring` （或 libsecret 支援 keyring-Kwallet nepodporuje libsecret） | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` （或 libsecret 支援 keyring-Kwallet nepodporuje libsecret） | `desktop-file-utils xprop`

其他散發套件必須使用相同的程式庫，而套件名稱可能會有所不同。 您可以找到這些功能的一些[社群支援的散發套件的秘訣](#tips-for-unsupported-distros)一節。

### <a name="debian--ubuntu"></a>Debian / Ubuntu

程式庫可能會安裝在 Debian/Ubuntu 架構的散發套件上執行`sudo apt install <library-name>`終端機中。

針對 Ubuntu 架構包括 Mint 發行版本，請執行：

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Debian 9 和非 Ubuntu 下游的散發套件，請執行：

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

程式庫可能會安裝在 Fedora/CentOS/RHL 基礎發行版本上執行`sudo yum install <library-name>`終端機中。 比方說，這會安裝所有項目：

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>VS 程式碼 OSS 問題

> **Arch Linux/Manjaro 使用者：** 使用[visual studio 賣](https://aur.archlinux.org/packages/visual-studio-code-bin)AUR 封裝，若要避免這個問題。

任一 vanilla 或 VS 程式碼 OSS 的修改版本的 Visual Studio 程式碼封裝可以遺失的重要值`product.json`啟用時，防止 Visual Studio Live Share 的檔案。

若要查看您可能會遇到此問題的快速方法是移至說明 > [切換開發人員工具]，如果您發現指出 Live Share 延伸模組的堆疊追蹤，請參閱未啟動，因為它使用 「 建議的 API 」。

若要確認這是您的問題，請檢查的內容`product.json`。 檔案的位置會因這個封裝，但它通常是在下列位置：

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

如果`extensionAllowedProposedApi`屬性遺漏或不會看到 「 ms-vsliveshare.vsliveshare 」 參考，您使用的 OS 版本與此問題。

作為**因應措施**，您可以新增下列內容輸入 product.json:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

請參閱[上述](#tips-for-community-supported-distros)如您所使用的散發套件是否已知運作的其他詳細資料。

## <a name="linux-browser-integration"></a>Linux 瀏覽器整合

Visual Studio 即時共用通常**不需要額外的安裝步驟**若要啟用在 Linux 上的瀏覽器整合。

若要這麼做，Live Share 會自動放在桌面檔案`~/.local/share/applications`和必要的啟動器本身在`~/.local/share/vsliveshare`先初始化延伸模組。 如果成功的話，不需要採取任何動作。

在某些情況下，發行版本不是支援此位置或需要取得它與他們開啟了香草的安裝搭配運作的調整。 在這些情況下，Live Share 退而使用`/usr/local/share`改。 如此一來，**您可能會收到通知您的系統管理員 (sudo) 密碼，就需要**完成安裝程序。 終端機視窗會出現告知您要安裝的瀏覽器啟動。 只要輸入您的密碼提示時，並按 enter 鍵以關閉 終端機視窗中的安裝完成之後。

如果您希望自己執行命令相反地，您可以按一下"改為複製 」 這會改為將終端機命令複製到剪貼簿。

最後，如果您選擇完全略過此步驟中，您仍然可以[以手動方式加入共同作業的工作階段](../use/vscode.md#join-manually)，但是不能加入瀏覽器中開啟 [邀請] 連結。 請注意，您永遠可以存取此命令一次更新的版本，點擊**Ctrl + Shift + P / Cmd + Shift + P** ，然後選取 「 即時共用：啟動器 Setup"命令。

## <a name="see-also"></a>另請參閱

- [操作說明：使用 Visual Studio Code 進行共同作業](../use/vscode.md)
- [Live Share 的連線需求](connectivity.md)
- [Live Share 的安全性功能](security.md)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
