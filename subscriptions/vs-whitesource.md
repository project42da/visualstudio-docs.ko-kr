---
title: "WhiteSource Bolt 혜택"
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 10/3/2017
Ms.topic: Get-Started-Article
Description: Learn how to activate the WhiteSource Bolt subscription included with your Visual Studio subscription.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: e8b5e08178ac35e57350052e6a9076dc0f80dca6
ms.sourcegitcommit: b7d3b90d0be597c9d01879338dd2678c881087ce
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2017
---
#  <a name="activating-the-whitesource-bolt-benefit-in-visual-studio-subscriptions"></a>Visual Studio 구독에서 WhiteSource Bolt 혜택 활성화

오픈 소스 취약성을 찾아 해결하고, 빌드에 포함된 모든 오픈 소스 구성 요소에 대한 포괄적인 인벤토리 및 라이선스 보고서를 생성합니다.  Enterprise 구독에는 체험 6개월 구독이 포함되어 있습니다. 

1.  WhiteSource Bolt 혜택을 사용하려면 혜택 타일의 아래쪽에 있는 **코드 가져오기** 링크를 클릭합니다.    

    ![WhiteSource 혜택 타일](_img\vs-whitesource\vs-whitesource-tile.png)

2.  활성화 코드가 표시된 알림을 받게 됩니다.  **클립보드에 코드를 복사**한 다음 **활성화**를 클릭합니다. 

    ![WhiteSource 혜택 코드 ](_img\vs-whitesource\vs-whitesource-code.png)

3.  WhiteSource 웹 페이지에서 **활성화** 단추를 클릭하거나 페이지의 **계정 활성화** 섹션까지 아래로 스크롤합니다.  

    ![WhiteSource 혜택 활성화](_img\vs-whitesource\vs-whitesource-activate-page-cropped.png)

4.  페이지의 **계정 활성화** 섹션에서 4개 단계를 안내받습니다.
- Microsoft Visual Studio 마켓플레이스에서 WhiteSource Bolt 확장을 [설치](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt)합니다. 확장을 설치할 수 있는 권한이 없는 경우 [이 페이지](https://www.visualstudio.com/en-us/docs/marketplace/get-vsts-extensions#request)를 방문하세요.

    VSTS를 사용하는 경우 녹색 **설치** 단추를 클릭하거나 Team Foundation Server에 대한 **다운로드** 단추를 클릭합니다.  이 예에서는 VSTS를 사용합니다. 

    ![WhiteSource 혜택 확장 설치](_img\vs-whitesource\vs-whitesource-download-install.png)

- 그런 다음 사용하려는 VSTS 계정을 선택하고 **확인**을 클릭합니다.  (아직 VSTS를 설정하지 않은 경우 [혜택](https://my.visualstudio.com/benefits) 페이지를 방문하여 VSTS 혜택을 활성화합니다.)

    ![WhiteSource 혜택 계정 확인](_img\vs-whitesource\vs-whitesource-confirm-account.png)

- 확장이 설치되어 사용할 준비가 되었는지 확인하는 메시지가 표시됩니다.  **시작**을 클릭하여 WhiteSource Bolt 페이지로 돌아갑니다.  

    ![WhiteSource 혜택 설치 완료](_img\vs-whitesource\vs-whitesource-install-complete.png)

5.  VSTS(Visual Studio Team Services) 프로젝트 대시보드를 열고 **빌드 및 릴리스** 메뉴를 클릭하고 **WhiteSource Bolt**를 선택합니다.

    ![WhiteSource 혜택 확장 추가](_img\vs-whitesource\vs-whitesource-installed-cropped.png)

6. WhiteSource Bolt 혜택 타일에서 활성화 코드를 붙여넣고 **활성화**를 클릭합니다. 각 활성화 코드는 하나의 프로젝트만 활성화하는 데 사용할 수 있습니다. 

    ![WhiteSource 혜택 활성화 코드](_img\vs-whitesource\vs-whitesource-activate-code-cropped.png)

7.  이제 활성화가 완료되었으며, 남아 있는 구독 기간은 180일입니다. 
8.  WhiteSource Bolt 확장을 빌드 단계 중 하나로 추가해야 합니다.  [WhiteSource Bolt 페이지](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate)에서 사용 방법을 보여 주는 비디오가 제공됩니다.  
9. 빌드를 실행하면 다음과 같은 포괄적인 보고서와 대시보드가 자동으로 생성됩니다.
- 보안 취약성 대시보드
- 보안 취약성 보고서
- 오래된 라이브러리 보고서
- 라이선스 위험 및 규정 준수 대시보드
- 인벤토리 보고서
