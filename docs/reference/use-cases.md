---
title: 常見使用案例-Visual Studio 即時共用 |Microsoft Docs
description: 開發人員通常會運用 Visual Studio Live Share 的使用案例的概觀。
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: d4dc3f2a6dfd8e0951a944cf4f487cedc49e4370
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640142"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>常見使用案例

Visual Studio Live Share 的主要目標是要讓開發人員彼此共同作業更容易，且不會造成任何意見，關於何時及如何執行此動作 （例如通訊使用的工具，「 右邊 」 軟體方法或 SCM 工作流程）。 如此一來，您的工具可支援所發生的互動**自然**，並做為 **經常*如有需要但在方法中，**贈*您已經想運作。

此文件會醒目顯示某些使用案例，Visual Studio Live Share，已在使用，並且描述以及我們目前支援，以及我們計劃將它們最佳化進一步 （根據意見反應 ！） 的方式。 如果您使用 Live Share 已經未涵蓋如下的項目，或您認為我們可以如何進一步支援特定的使用案例，請[讓我們知道](https://github.com/MicrosoftDocs/live-share/issues/new)。

- [快速協助](#quick-assistance)
    - [辦公時間](#office-hours)
- [配對程式設計](#pair-programming)
    - [Mob 程式設計](#mob-programming)
    - [程式碼撰寫競賽 / Hack-A-Thons](#coding-competitions--hack-a-thons)
    - [學校群組專案](#school-group-projects)
    - [資料流的開發人員](#developer-streaming)
    - [建立原型 / 專案起始](#prototyping--project-inception)
- [互動式教育版](#interactive-education)
    - [對等顧問 / 上架](#peer-mentoring--onboarding)
    - [小組的棕色袋子](#team-brown-bags)
    - [課堂課程](#classroom-lectures)
- [程式碼檢閱](#code-reviews)
- [技術面試](#technical-interviews)

## <a name="quick-assistance"></a>快速協助

當您遇到問題 （例如嘗試解決 bug，設定您的環境） 時，您可以使用 Visual Studio Live Share 立即尋求從另一個對等的協助。 在許多情況下，它不是立即清除需要協助的人員，內容，因此，Live Share 的協助，藉由讓您簡單以存取您的整個專案，而且如果/為所需，以累加方式會共用更多 （例如本機伺服器，唯讀終端機）。 上一步往來傳送程式碼片段和/或錯誤訊息不需要 ！

此外，因為 Live Share 可讓您不需要安裝任何必要的平台 Sdk （例如 Node.js、 Go、.NET Core） 的 「 來賓 」 或工具擴充功能，共用您的使用中偵錯工作階段，它可以協助您取得更快的解決方式，並防止 「 不我的電腦上重現 」 的情況。 即時共用可讓您與他人，分享偵錯狀態，針對任何程式設計語言或執行階段環境 (例如 Kubernetes，React Native 應用程式)，因此無論您需要協助，您可以使用共用 ！

### <a name="office-hours"></a>辦公時間

許多企業和教育機構 （例如學校、 線上訓練課程） 提供支援給客戶/員工/學生在預先決定的時間，同時通常依週期性頻率 （例如每個星期五的 3 至下午 5 點）。 如此一來，"office hours"會是直接排程的形式顯示的 [快速協助]，相對於完全在臨機操作。 即時共用可讓您更容易獲得協助快速，因為 「 專家 」 提供的說明可以立即加入共同作業工作階段，並回答您的問題，而不需要完全設定他們的機器。

## <a name="pair-programming"></a>配對程式設計

其中一個最常使用的案例，Visual Studio Live Share 為 」 配對程式設計 」: 兩個或多個開發人員，一起運作，在共用的工作，其目標是分享知識，以提高小組一致性，和甚至是產品的品質。 確切的外觀與風格的配對程式設計可以很大的差異小組和情況下，根據下列 （還有其他）：

1. 「 工作 」 (例如 bug、 使用者劇本) 所共同編撰的範圍

1. 預期的持續時間的共同作業工作階段 （例如兩分鐘，全職一小時、 每週一次，TBD）

1. 人數涉及 （例如兩個，整個小組）

1. 每個參與者 （例如 「 驅動程式 」，觀察者/檢閱者，主題專家） 的角色

1. 鄰近程度參與者 （例如共置於同一個建築物，世界各地）

即時共用被設計為無從驗證所有先前提及的考量，以及反而致力於支援配對程式設計，而且完全 「 隨機 」 建立您的情況。 話雖如此，不像兩位開發人員共用單一鍵盤和螢幕，Live Share 可讓一種可讓開發人員使用共用的目標，但不會移除其個別的自我管理或環境喜好設定的配對程式設計。 您可以獨立運作，或放在一起，讓每個參與者，將自己以為的共同作業的程序。

若要進一步支援配對程式設計，並允許每個 「 來賓 」 來執行常用動作，我們必須有工作在我們的規劃，持續增加的內容和 Live Share 工作階段中共用的功能： 工作 ([#40](https://github.com/MicrosoftDocs/live-share/issues/40))，建置輸出 ([#48](https://github.com/MicrosoftDocs/live-share/issues/48))，客體驅動的偵錯 ([#32](https://github.com/MicrosoftDocs/live-share/issues/32))，和更多功能。 讓我們知道哪一種體驗會對您而言重要 ！

若要更進一步向下中斷此使用案例中，下列項目代表的配對程式設計，我們觀察到使用即時共用的人的表單：

### <a name="mob-programming"></a>Mob 程式設計

[Mob 程式設計](https://en.wikipedia.org/wiki/Mob_programming)（或 swarm 程式設計） 基本上是配對程式設計，但與兩個以上的人員。 因此，套用所有的配對程式設計的優點的 Live Share 一樣也一樣。 此外，某些小組會執行"swarming 」 做為所需的為基礎 （例如小組 rallying 周圍消防演習） 而不全職員工。

目前，Live Share 支援最多五個來賓工作階段中，這可能會或可能不會配合您小組的大小。 不過，這是我們想要增加 （適用於各種使用案例），而且想要的意見反應的項目 ([投票👍這裡](https://github.com/MicrosoftDocs/live-share/issues/229))

### <a name="coding-competitions--hack-a-thons"></a>程式碼撰寫競賽 / Hack-A-Thons

程式碼撰寫競賽和駭客的 thons 是有效的短期、 單一工作的變化 mob 程式設計。 小組成員和其目前的角色的成員也是可能動態的。 因為這個使用案例也通常是時間緊迫，不需要採用全新的工具，而且能夠搭配使用，不侷限於單一畫面或鍵盤，可以移以遞增的記錄方式，在即時共同作業的能力速度。

因為在此環境中的參與者可能永遠無法完全 「 受信任 」，我們聽說允許的要求移除 （並封鎖） 來賓與工作階段，在任何時間，也就是我們計劃啟用的項目 ([#398](https://github.com/MicrosoftDocs/live-share/issues/398))，並支援提供完整掌控其環境中的 [主機] 的目標。

### <a name="school-group-projects"></a>學校群組專案

群組看起來就 mob 程式設計，在多個學生會放在一起，處理像是許多專案結束，而且可以將焦點放在單一工作，或同時處理個別的工作之間的順暢地轉換。 而不是只依賴版本控制以共同作業以非同步方式，他們可以使用 Live Share 工作即時的方式，可協助處理群組中的社交及教育優勢。

### <a name="developer-streaming"></a>資料流的開發人員

資料流 （透過 Twitch 或 Mixer） 的開發人員已經成為吸引人新形式的教育。 雖然 Live Share 並非要取代其廣播平台 （雖然我們已聽到要求 ！），但是它提供一種方法的程式使用一或多個來賓，主應用程式組，然後再串流處理該互動。 如此一來，檢視器可能深入查看自然互動與兩個或多個開發人員而言，可能甚至會一起運作中完全不同的作業系統和 Ide 的思考過程 ！

### <a name="prototyping--project-inception"></a>建立原型 / 專案起始

當小組正在啟動新的專案/微服務，或建立原型/峰值的新功能時，通常是很有幫助一起共同作業，以便快速進展，並探索新構想。 由於新 forming 的程式碼基底可能不共用的存放庫尚未認可，Live Share 可讓所有人都能參與反覆的程序，不論如果它們在同一個辦公室或不。

## <a name="interactive-education"></a>互動式教育版

一般而言，Live Share 致力於協助開發人員分享其小組之間的知識。 教育版是 Live Share 的基本使用案例，它支援這尤其藉由與程式碼基底所共同編撰，而不只觀看螢幕進行互動的每個參與者。 每個人都了解一些微妙的差異，以不同方式，因此，提供在 「 學生 」 獨立性，他們就能夠利用，而不必犧牲其能夠瀏覽他們自己的想法，過程中所提供的指示。

### <a name="peer-mentoring--onboarding"></a>對等顧問 / 上架

當引進新的程式碼基底開發人員，功能區、 技術等您可用來引導他們逐步完成專案 Live Share (使用`Follow Mode`)，使得它們可以依照您，但從自己的個人 IDE 中。 由於 Live Share 可讓 「 來賓 」 以獨立瀏覽專案 (例如開啟檔案、 執行`Peek Definition`)，則可以依照下列允許，但同時，快速瀏覽視需要執行 （例如：「 嗯，這個函式的作用為何？ 」）。

### <a name="team-brown-bags"></a>小組的棕色袋子

小組棕色袋子就像是顧問的對等的有效但呈現給整個小組，以及甚至是其他著重於 socializing 通常很有用的知識，而不是上架支援和/或與特定的工作協助。

### <a name="classroom-lectures"></a>課堂課程

當講師教學課程中時，他們可以使用 Live Share 與學生，而不是直接呈現其螢幕共用其專案。 這可讓整個類別，若要依照老師，同時能夠與他們自己的專案互動。 此外，老師可以要求個別的學生，以協助解決本課程的特定部分 （例如：「 哪一種方法應該我們呼叫這裡？ 」），這可以幫助的類別，社會層面不要求學生走向前面的空間，或甚至是實際出現在同一個房間內 （例如線上課程） 中。

為了協助在課堂中，Live Share 可讓唯讀模式中的共用。 講師可以使用唯讀模式，使其能夠與學生分享其專案，而不必擔心不必要或意外所做的編輯。

此外，Live Share 具有實驗性支援，可讓聯結成共同作業工作階段的最多 30 來賓。 如此一來，講師可以有其整個類別加入到工作階段，並同時檢視程式碼。

若要啟用此實驗性功能：

- **VS 程式碼：** 將 「 liveshare.features":"experimental"新增至 settings.json 中。
- **VS:** 設定工具 > 選項 > 即時共用 > 要 「 實驗性 」 的功能

若要完全最佳化 Live Share 此案例中，我們需要以進一步提高目前的客體限制 ([#229](https://github.com/MicrosoftDocs/live-share/issues/229))，並簡化會起始工作階段的方式 ([#422](https://github.com/MicrosoftDocs/live-share/issues/422))。

## <a name="code-reviews"></a>程式碼檢閱

Pr 是強大的方式，與其他人共同作業，但通常代表完成工作 （不含"WIP"提取要求），並想来合併中。 許多次的提取要求中提供的意見反應可以輕鬆地已提供稍早，因此，有可能讓團隊可以輕鬆地持續搜尋建議，從其對等，而不是等待，直到它們會 「 完成 」 的工作要求的值。

Live Share 可讓您立即與其他人共用您的專案，因為它可以用來啟用 「 非正式"/，而不尋求協助，您要直接搜尋輸入，確保您的方向和/或方法的特定程式碼檢閱與其他人。 這可能有助於後續 Pr 更快速、 完成和絕對協助交際整個團隊的知識。

此外，因為 Live Share 可讓您共用的任意的目錄，您可以使用它來執行程式碼檢閱，即使您目前未使用版本控制 （不過您應該 ！），或如果您的小組不會使用提取要求 （例如 你主幹型開發）。

即時共用目前不共用原始檔控制差異比對，使用程式碼檢閱時，這會是重要的一項內容。 這是在我們的規劃，而且優先權上的任何意見反應誠摯 ([投票👍這裡](https://github.com/MicrosoftDocs/live-share/issues/36))。

## <a name="technical-interviews"></a>技術面試

當面試適合開發人員的位置，通常是有幫助超越白板討論區，相反地，觀察它們解決實際的 IDE 中的編碼問題 (特別是如果您的小組/組織已 「 標準化 」 工具上，您想要查看使用它們）。 這不只提供它們的優點可能更自然/舒適 （大部分的開發人員沒有程式碼在白板上 ！） 的方式工作，但同時，讓他們立即意見反應/協助在工作時 （例如建置錯誤，intellisense）。 許多次，是了解求職者的思考過程，而不是確切的語法及/或 API 名稱記下其能夠更加重要。 如此一來，Live Share 可提供類似執行程式設計工作階段中，一組可讓參與者在其自己的環境 （包括作業系統設定，例如協助工具），但會照樣體驗為本機或遠端的訪談。

此外，真實世界的開發更不只撰寫程式碼。 由於 Live Share 也支援共用的偵錯、 工作和終端機，它可讓觀察候選項目時診斷問題，並提供適當的工具來解決它 （例如步驟偵錯、 執行測試） 所需的面試。 由於所有的內容是從主機電腦以遠端方式運作，候選項目可以快速跳至 「 訪談環境 」，而不需要設定其電腦 （除了安裝 Live Share）。 小組無法再維護資料的儲存機制共用面試應用程式 （或使用其實際的產品程式碼基底），可以複製並與共用的候選項目，只要將它們傳送每個面試之前的工作階段 URL。

## <a name="see-also"></a>另請參閱

- [語言和平台支援](platform-support.md)
- [Live Share 的連線需求](connectivity.md)
- [Live Share 的安全性功能](security.md)
- [所有主要 Bug、功能要求和限制](https://aka.ms/vsls-issues) \(英文\)
- [所有功能要求和限制](https://aka.ms/vsls-feature-requests) \(英文\)

有問題嗎？ 請參閱[疑難排解](../troubleshooting.md)或[提供意見反應](../support.md)。
