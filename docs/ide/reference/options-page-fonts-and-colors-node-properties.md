---
title: "옵션 페이지, 글꼴 및 색 노드 속성 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
caps.latest.revision: 8
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: b54f38aa51904ca502ab7298359fdc7124a807a9
ms.lasthandoff: 02/22/2017

---
# <a name="options-page-fonts-and-colors-node-properties"></a>옵션 페이지, 글꼴 및 색 노드 속성
이 문서에서는 **옵션** 대화 상자의 **환경** 범주에 있는 **글꼴 및 색** 범주 아래에 표시되도록 등록된 도구 창의 글꼴 및 색 속성을 설명합니다. 이는 VSPackage가 설치 또는 제거될 경우 변경할 수 있는 색 항목 그룹의 동적 특성을 지원합니다.  
  
 다음 섹션에서는 등록된 창 형식의 예제와 각 창에 사용할 수 있는 속성을 보여 줍니다.  
  
## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>텍스트 편집기 또는 프린터 또는 대화 상자 및 도구 창  
 `DTE.Properties("FontsAndColors", "TextEditor")`  
  
 또는  
  
 `DTE.Properties("FontsAndColors", "Printer")`  
  
 또는  
  
 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`  
  
|속성 항목 이름|값|설명|  
|------------------------|-----------|-----------------|  
|FontFamily|Get/Set(문자열)|사용할 글꼴 이름(예: "Courier New").|  
|FontCharacterSet|Get/Set(<xref:EnvDTE.vsFontCharSet>)|사용할 문자 집합의 형식을 지정하는 <xref:EnvDTE.vsFontCharSet> 값(예: 히브리어 또는 러시아어).|  
|FontSize|Get/Set(Short)|사용할 글꼴 크기(포인트). 예: 10 또는 12.|  
  
## <a name="see-also"></a>참고 항목  
 [옵션 설정 제어](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [옵션 페이지에서 속성 항목의 이름 확인](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [옵션 페이지, 환경, 노드 속성](../../ide/reference/options-page-environment-node-properties.md)   
 [옵션 페이지, 텍스트 편집기 노드 속성](../../ide/reference/options-page-text-editor-node-properties.md)
