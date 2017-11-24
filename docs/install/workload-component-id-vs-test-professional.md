---
title: "Visual Studio Test Professional 2017 작업 및 구성 요소 ID | Microsoft Docs"
description: "Visual Studio 작업 및 구성 요소 ID를 사용하여 테스터를 위한 통합된 테스트 도구를 제공합니다."
keywords: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.date: 10/09/2017
ms.topic: article
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: 
ms.technology: vs-ide-install
ms.assetid: 70c03438-8434-4921-ada0-c172519af431
ms.openlocfilehash: 82375aa5b08b3890aa2c615f9d44877ca7fb3a22
ms.sourcegitcommit: 2c7f48ad6073a81fa927568793633f26cc1f0b15
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2017
---
# <a name="visual-studio-test-professional-2017-component-directory"></a>Visual Studio Test Professional 2017 구성 요소 디렉터리

이 페이지의 표에는 명령줄을 사용하여 Visual Studio를 설치하는 데 사용할 수 있는 ID가 나열되어 있습니다. Visual Studio에 대한 업데이트를 릴리스할 때 추가 구성 요소가 추가될 것입니다.

또한 이 페이지에 대해 다음 사항에 유의하세요.

* 각 작업에는 고유한 섹션 및 작업 ID와 해당 작업에 사용할 수 있는 구성 요소 표가 있습니다.
* 기본적으로 **필수** 구성 요소는 작업을 설치할 때 설치됩니다. 원하는 경우 **권장** 및 **선택적** 구성 요소를 설치할 수도 있습니다.
* 작업과 관련이 없는 추가 구성 요소를 나열하는 섹션도 추가했습니다.

이러한 ID를 사용하는 방법에 대한 자세한 내용은 [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md) 페이지를 참조하세요. 다른 제품의 작업 및 구성 요소 ID 목록은 [Visual Studio 2017 작업 및 구성 요소 ID](workload-and-component-ids.md) 페이지를 참조하세요.

## <a name="test-professional"></a>Test Professional

**ID:** Microsoft.VisualStudio.Workload.TestProfessional

**설명:** Test Professional은 테스터를 위한 통합된 테스트 도구를 제공하여 테스트 수명 주기 전반에 걸쳐 테스트 요구 사항에 맞게 작동합니다.

### <a name="components-included-by-this-workload"></a>이 작업에 포함되는 구성 요소

구성 요소 ID | 이름 | 버전 | 종속성 유형
--- | --- | --- | ---
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Feedback Client | 15.0.26711.1 | 필수
Microsoft.VisualStudio.Component.TestTools.MicrosoftTestManager | Microsoft Test Manager | 15.0.26606.0 | 필수

## <a name="unaffiliated-components"></a>독립적 구성 요소

이러한 구성 요소는 작업에 포함되지 않지만 개별 구성 요소로 선택할 수 있습니다.

구성 요소 ID | 이름 | 버전
--- | --- | ---
해당 없음 | 해당 없음 | 해당 없음

## <a name="get-support"></a>지원 받기
때로는 무엇인가 잘못될 수도 있습니다. Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지에서 문제 해결 팁을 참조하세요. 또한 Visual Studio IDE의 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 제품 문제를 보고하거나 [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 제안을 공유할 수 있습니다. [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다. [Gitter 커뮤니티](https://gitter.im/Microsoft/VisualStudio)([GitHub](https://github.com/) 계정 필요)의 Visual Studio 관련 대화를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.

## <a name="see-also"></a>참고 항목

* [Visual Studio 작업 및 구성 요소 ID](workload-and-component-ids.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 설치](use-command-line-parameters-to-install-visual-studio.md)
  * [명령줄 매개 변수 예](command-line-parameter-examples.md)
* [Visual Studio의 오프라인 설치 만들기](create-an-offline-installation-of-visual-studio.md)
