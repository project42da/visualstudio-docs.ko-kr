---
title: "방법: Office 다국어 사용자 인터페이스 대상 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- globalization [Office development in Visual Studio], user interface targeting
- MUI [Office development in Visual Studio]
- Office applications [Office development in Visual Studio], localization
- Multilingual User Interface [Office development in Visual Studio]
- localization [Office development in Visual Studio], user interface targeting
- Office applications [Office development in Visual Studio], globalization
ms.assetid: b1f03164-f0cf-42e3-942b-8cf90c242ffb
caps.latest.revision: "30"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3ee88cbcde2a25a13b4c4432afe5a5b1397ab727
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-target-the-office-multilingual-user-interface"></a>방법: Office 다국어 사용자 인터페이스 대상 선택
  인터페이스 MUI (다국어 사용자)는 최종 사용자의 사용자 인터페이스 (UI) 언어를 변경 하는 기능을 제공 하는 Microsoft Office 기능입니다. 예를 들어 영어 UI를 사용 하는 최종 사용자 스페인어로 UI의 언어를 변경할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 응용 프로그램의 Office 여러 언어를 사용 하는 사람에 의해 사용 됩니다 (사용자에 게 설치 하는 올바른 리소스) 하는 경우 사용자의 컴퓨터에 Office에서 사용 되는 언어와 일치 하도록 UI 문자열의 언어를 자동으로 변경 하는 코드를 추가할 수 있습니다.  
  
### <a name="to-check-the-current-office-ui-setting"></a>현재 Office UI 설정을 확인 하려면  
  
1.  사용 하 여는 <xref:System.Threading.Thread.CurrentUICulture%2A> 현재 스레드의 속성입니다. 현재 사용자의 컴퓨터에서 실행 하는 Office 버전에서 사용 되는 언어와 일치 하도록 UI 문자열의 언어를 설정 합니다.  
  
     [!code-vb[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreCreatingExcelVB/Sheet1.vb#10)]
     [!code-csharp[Trin_VstcoreCreatingExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreCreatingExcelCS/Sheet1.cs#10)]  
  
## <a name="see-also"></a>참고 항목  
 [How to: Target Office Applications Through Primary Interop Assemblies](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)   
 [Office 솔루션에서 런타임에 바인딩](../vsto/late-binding-in-office-solutions.md)  
  
  