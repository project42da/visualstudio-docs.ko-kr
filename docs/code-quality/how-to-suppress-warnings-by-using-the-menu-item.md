---
title: "방법: 메뉴 항목을 사용 하 여 경고 표시 안 함 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- warnings, suppressing
- code analysis, suppressing warnings
ms.assetid: 36bd1850-dcde-4ed0-9bc3-0b83df434362
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 5ce2369b5b97f1767a17686d3de2d4127150c05d
ms.sourcegitcommit: 9a2f937e42305db6e3eaa7aadc235b0ba9aafc83
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2018
---
# <a name="how-to-suppress-warnings-by-using-the-menu-item"></a>방법: 메뉴 항목을 사용하여 경고 표시 안 함
> [!NOTE]
>  웹 사이트 프로젝트에서는 ISS(In source suppression)가 지원되지 않습니다.  
  
 코드 분석 창을 사용하면 코드 분석 경고 표시를 숨길 수 있습니다. 경고 표시 숨김은 경고를 비활성화하는 것과 다릅니다. 경고를 표시 하는 경우 위반의 특정 인스턴스에만 적용 됩니다. 오류 목록 창에는 같은 경고 다른 위반이 보고 됩니다.  
  
 코드 분석을 실행한 후 코드 분석 창에 표시된 하나 이상의 코드 분석 경고가 응용 프로그램에 해당되지 않는 것인지 확인할 수 있습니다. 예를 들어 코드 올바른지 확인할 수 있습니다. 또는 일부 위반 낮은 우선 순위 이며 현재 개발 주기에서 수정 되지 않는 경우 수도 있습니다. 이 이유를 알고 코드를 검토 하 고 경고를 표시 될 수 있습니다 결정 했음을 팀 구성원에 게 알리기 위해 경고가 임을 나타내려면 좋습니다. ISS(In Source Suppression)는 경고가 생성되는 지점에 가깝게 표시 숨김을 설정할 수 있기 때문에 유용합니다.  
  
 소스 코드에 또는 전역 억제 (suppression) 파일에는 억제 (suppression)를 표시할지 여부를 선택할 수 있습니다. 일부 비 표시 오류 전역 억제 (suppression) 파일에 배치 되어야 합니다. 이 경우는 **소스** 옵션이 비활성화 됩니다.  
  
### <a name="to-suppress-a-warning-by-using-menu-item"></a>메뉴 항목을 사용 하 여 경고를 표시 하려면  
  
1.  에 **분석** 메뉴 선택 **Windows** 선택한 후 **코드 분석**합니다.  
  
2.  에 **코드 분석** 창에서 경고 숨김을 선택 합니다.  
  
3.  작업을 선택한 다음 선택 **메시지 표시 안 함**, 다음 중 하나를 선택 하 고 **소스** 또는 **프로젝트 억제 (suppression) 파일에서**합니다.  
  
     해당 경고가 표시되지 않고, 취소선이 그려진 상태로 경고가 코드 분석 창에 나타납니다.  
  
> [!NOTE]
>  대상을 갖지 않는 비 표시 오류 전역 억제 (suppression) 파일에 나타납니다.