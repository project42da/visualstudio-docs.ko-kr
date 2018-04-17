---
title: 레거시 언어 서비스에서 자동 서식을 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e052c62afcf9551cc54373da15071fb3903fe950
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>자동 레거시 언어 서비스에서 형식 지정
자동 서식을 사용 하 여 언어 서비스는 자동으로 코드 조각을 삽입 코드의 사용자가 알려진된 코드 구문을 입력 하기 시작할 때입니다.  
  
## <a name="automatic-formatting-behavior"></a>자동 서식 동작  
 예를 들어 입력 `if`, 일치 하는 중괄호를 자동으로 삽입 하는 언어 서비스 또는 ENTER 키를 누를 경우 언어 서비스를 강제로 삽입 지점이 새 줄에 적절 한 들여쓰기 수준을 인지 여부에 따라 이전 줄 새 범위를 엽니다.  
  
 자동 서식 지정에 대 한 언어 서비스의 나머지 부분에 사용 되는 명령 필터를 사용할 수도 있습니다. 호출 하 여는 중괄호를 강조 표시도 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [레거시 언어 서비스 개발](../../extensibility/internals/developing-a-legacy-language-service.md)