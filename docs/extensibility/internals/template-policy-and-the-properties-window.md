---
title: 정책 템플릿 및 속성 창 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Properties window, template policy
ms.assetid: 1d8019d3-5e57-47ba-b358-526b0796a63b
caps.latest.revision: 15
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 51735bf0f46e5a1ead6f989a8e75745ebc8e6e35
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="template-policy-and-the-properties-window"></a>정책 템플릿 및 속성 창
프로젝트는 엔터프라이즈 템플릿 프로젝트 내에 포함 되 면 하는 경우 해당 엔터프라이즈 템플릿 프로젝트 정책을 적용할 수 있습니다. 템플릿 정책을 속성에 대 한 기본값 설정, 속성 숨기기, 속성을 추가 및 등을 사용할 수 있는 제약 시스템 됩니다.  
  
 서식 파일 정책을 사용 하 여 정보 표시를 제어 하는 **속성** 창 구현 간에 차이가 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>합니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>템플릿 정책 제한 솔루션 또는 프로젝트 수준에서 개체 속성을 사용할 수 있지만 구성 요소 수준에서 개체 속성을 처리 합니다. 즉  
  
-   메서드를 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing> 에 표시 될 내용을 결정 하는 **속성** 특정 개체에 대 한 창  
  
-   솔루션 및 프로젝트 수준에서 템플릿 정책을 사용 하 여에 표시 될 내용을 결정 하는 **속성** 이전에 지정한 개체에 대 한 창  
  
 서식 파일 정책을 사용 하 여 특정 속성을 선택적으로 제한 하는 **속성** 했을 때 지정 된 형식의 프로젝트 항목 창에서 선택한 **솔루션 탐색기** 의 모든 구성원에 게 도움이 될 수 개발 팀 프로젝트에서 작업 합니다. 예를 들어 템플릿 정책을 사용 하 고 있는 모든 연결 문자열 정보를 데이터베이스에서 개발자를 위한를 읽기 전용 연결 문자열을 확인 합니다. 이러한 방법으로 데이터 액세스에 대 한 올바른 경로 사용 하는 각 개발자가 하는 간단한 방법을 제공할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing>   
 [속성 확장](../../extensibility/internals/extending-properties.md)