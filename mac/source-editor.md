---
title: "소스 편집기"
description: "Mac용 Visual Studio에서 소스 편집기 사용"
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: A018A314-C1C4-4F36-BCB6-2D434208FCFE
ms.translationtype: HT
ms.sourcegitcommit: e2b7ff9126e1cc38ac2e58d6be339b656a024e7f
ms.openlocfilehash: aa7635cd2593b871128c0588110f0bfdad5a82ec
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---

# <a name="source-editor"></a>소스 편집기

코드를 간결하고 효율적으로 작성하려면 신뢰할 수 있는 소스 편집기가 꼭 필요합니다. Mac용 Visual Studio에서 제공하는 정교한 소스 편집기는 IDE 상호 작용의 핵심을 이룹니다. 소스 편집기는 구문 강조 표시, 코드 조각, 코드 접기 등의 기초적인 기능부터 Roslyn 컴파일러 통합에 따르는 완벽한 기능의 IntelliSense 코드 완성과 같은 이점에 이르기까지 작업의 편의성을 높여 주는 기능을 다양하게 제공합니다.

Mac용 Visual Studio의 소스 편집기에서 IDE가 제공하는 디버깅, 리팩터링, 버전 제어 통합 등의 기타 기능을 원활하게 사용할 수 있습니다.

이 항목에서는 소스 편집기의 주요 기능 중 일부를 소개하고 Mac용 Visual Studio의 생산성을 극대화하는 방법을 살펴봅니다.

## <a name="the-source-editor-experience"></a>소스 편집기 환경

코드 전체를 효율적으로 보면서 탐색하는 작업은 개발 워크플로에서 필수적인 부분입니다. 코드를 살펴보고 유지 관리하는 방법은 개발자 개인마다 다르며, 프로젝트마다 다르기도 합니다.

Mac용 Visual Studio는 플랫폼 간 개발을 최대한 편리하고 실용적으로 진행할 수 있도록 하는 효과적인 기능을 다양하게 제공합니다. 아래 섹션에서는 몇 가지 주요 기능을 설명합니다.


### <a name="code-folding"></a>코드 접기

개발자는 코드 접기를 사용하여 using 지시문, 상용구 코드 및 주석, #region 명령문 등의 전체 코드 섹션을 표시하거나 숨김으로써 대규모 소스 코드 파일을 더욱 쉽게 ​​관리할 수 ​​있습니다. 이 기능은 Mac용 Visual Studio에서 기본적으로 해제되어 있습니다.

코드 접기를 사용하도록 설정하려면 **Visual Studio > 기본 설정... > 텍스트 편집기 > 일반 > 코드 접기**로 이동합니다.

![코드 접기 옵션](media/source-editor-image1.png)

이 메뉴에는 코드 접기를 사용하도록 설정하는 옵션 외에도 기본적으로 #regions 및 주석을 접고 코드 대신 명명된 힌트를 표시하는 옵션이 포함되어 있습니다.

섹션을 표시하거나 숨기려면 줄 번호 옆의 노출 위젯을 사용합니다.

 ![코드의 섹션 표시 또는 숨기기](media/source-editor-image2.png)

**보기 > 접기 > 접기 토글/모든 접기 토글** 메뉴 항목을 사용하여 접기 표시와 숨기기를 전환할 수도 있습니다.

 ![접기 메뉴 항목](media/source-editor-image19.png)

이 메뉴 항목으로 코드 접기를 사용하거나 사용하지 않도록 설정할 수도 있습니다.

### <a name="white-space"></a>공백

소스 코드에서 보이지 않는 문자를 표시해야 하는 경우도 있습니다. 이는 코딩 표준을 준수하고 불필요한 공간 낭비를 방지하는 수단이 됩니다. 또한 정확한 줄 들여쓰기가 품질을 좌우하는 F# 코드를 작성할 때 매우 유용합니다.

아래 그림과 같이 **Visual Studio > 기본 설정 > 텍스트 편집기 > 표식 및 눈금자**로 이동하여 공백을 표시하는 옵션을 설정합니다. 이 옵션을 선택하면 보이지 않는 문자를 표시하는 _시점_을 Never([안 함]), On Selection([선택 시]), Always([항상]) 중 하나로 설정할 수 있습니다.

 ![보이지 않는 문자 표시 옵션](media/source-editor-image3.png)

탭, 공백 및 줄 끝을 표시하는 옵션도 사용할 수 있습니다.

 ![탭 및 공백 표시](media/source-editor-image4.png)

 보이지 않는 문자는 아래 그림과 같이 회색 점으로 표시됩니다.

 ![공백 표시](media/source-editor-image22.png)


### <a name="ruler"></a>눈금자

열 눈금자를 표시하면 줄의 길이를 확인할 때, 특히 줄 길이를 규정해 놓은 팀에서 작업할 때 특히 유용합니다. 아래 그림과 같이 **Visual Studio > 기본 설정... > 텍스트 편집기 > 표식 및 눈금자**로 이동하고 **열 눈금자 표시**를 선택하거나 취소하여 열 눈금자를 켜고 끌 수 있습니다.

 ![](media/source-editor-image5.png)

 눈금자는 소스 편집기에서 연한 회색 선으로 표시됩니다.


### <a name="highlight-identifier-references"></a>식별자 참조 강조 표시

이 옵션을 사용하면 개발자가 소스 코드의 기호에 마우스 커서를 올려놓을 때 소스 편집기에서 해당 파일의 모든 기타 참조를 시각적으로 알려줍니다. 이 옵션을 사용하도록 설정하려면 아래 그림과 같이 **Visual Studio > 기본 설정... > 텍스트 편집기 > 표식 및 눈금자**로 이동하고 _식별자 참조 강조 표시_를 선택합니다.

![](media/source-editor-image6.png)

강조 표시의 색으로 할당 또는 참조 여부를 구분할 수도 있습니다. 할당은 빨간색으로, 참조는 파란색으로 강조 표시됩니다.

![](media/source-editor-image7.png)




