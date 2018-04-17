---
title: '방법: 기본 제공 색 항목을 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- colorable items
- language services, built-in colorable items
ms.assetid: 5e5f3436-6bad-4fd2-8823-6a30353ba648
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a6cf51516677aeca71dba269bcdd132e0830b6b4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-use-built-in-colorable-items"></a>방법: 기본 제공 색 항목 사용
기본 제공 색 항목을 사용 하기 전에 하면 먼저 알려야 통합된 개발 환경 (IDE)에 있는 경우 사용자 고유의 사용자 지정 색 항목을 제공 하지 않는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsProvideColorableItems> 개체입니다. 언어 서비스에 대 한 레지스트리 항목을 설정 하 여이 작업을 수행 합니다.  
  
### <a name="to-use-built-in-colorable-items"></a>기본 제공 색 항목을 사용 하려면  
  
1.  HKEY_LOCAL_MACHINE\VisualStudio에서\\*X.Y*\Languages\Language 서비스\\*언어 이름*여기서 *X.Y* 의버전이[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및 *언어 이름* 이름인 해당 언어의 이라는 DWORD 레지스트리 항목 값을 만들 `RequestStockColors`합니다.  
  
2.  설정의 `RequestStockColors` 레지스트리 항목 값을 1로 합니다.  
  
     레지스트리 항목에 색 지정 기의를 만든 후 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsColorizer.ColorizeLine%2A> 메서드의 멤버를 사용할 수는 <xref:Microsoft.VisualStudio.TextManager.Interop.DEFAULTITEMS> 편집기에서 사용 하기 위해 색 특성으로 이루어진 배열을 작성 하는 열거형입니다.  
  
    > [!NOTE]
    >  색 사용자 지정 항목을 제공 하는 경우에이 레지스트리 항목을 설정 하지 마십시오. 자세한 내용은 참조 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 편집기에서 색을 지정 하는 구문](../../extensibility/syntax-coloring-in-custom-editors.md)   
 [구문 색에 레거시 언어 서비스](../../extensibility/internals/syntax-coloring-in-a-legacy-language-service.md)   
 [구문 색 지정을 구현합니다.](../../extensibility/internals/implementing-syntax-coloring.md)   
 [사용자 지정 색 항목](../../extensibility/internals/custom-colorable-items.md)   
 [레거시 언어 서비스를 등록 하는 중](../../extensibility/internals/registering-a-legacy-language-service2.md)