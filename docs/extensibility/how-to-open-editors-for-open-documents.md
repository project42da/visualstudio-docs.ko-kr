---
title: "방법: 열려 있는 문서에 대 한 편집기를 열어 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], opening for open documents
ms.assetid: 1a0fa49c-efa4-4dcc-bdc0-299b7052acdc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dfd145281a467a23cd01d73ff04721d68580254e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-open-editors-for-open-documents"></a>방법: 열려 있는 문서에 대 한 편집기 열기
프로젝트 문서 창이 열리기 전에 프로젝트 먼저 결정 해야 여부는 파일이 이미 열려 다른 편집기에 대 한 문서 창에 있습니다. 파일은 프로젝트 관련 편집기에 열거나 수 또는 표준 편집기 중 하나에 등록 된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="opening-a-project-specific-editor"></a>프로젝트 관련 편집기 열기  
 다음 절차를 사용 하 여 이미 열려 있는 파일에 대 한 프로젝트 관련 편집기를 엽니다.  
  
#### <a name="to-open-a-project-specific-editor-for-an-open-file"></a>열려 있는 파일에 대 한 프로젝트 관련 편집기를 열려면  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A> 메서드를 호출합니다.  
  
     이 호출은 해당 하는 경우는 문서 계층, 계층 항목 및 창 프레임 포인터를 반환 합니다.  
  
2.  문서를 열면 프로젝트 또는 문서 뷰 개체도 제공 됩니다. 문서 데이터 개체로 존재 하는지 여부를 확인할를 확인 해야 합니다.  
  
    -   문서 보기 개체에 이미 있는 경우이 뷰는 다른 계층 또는 계층 항목에 대 한 프로젝트를 사용 하 여 보기의 창 프레임에 대 한 포인터 resurface 기존 창.  
  
    -   문서 보기 개체에 이미 있는 경우이 뷰는 동일한 계층 구조 및 계층 항목에 대 한 기본 문서 데이터 개체에 연결할 수 있는 프로젝트 보기를 열 수 있습니다. 그렇지 않으면 프로젝트를 기존 창 resurface 보기의 창 프레임에 대 한 포인터를 사용 해야 합니다.  
  
    -   문서 데이터 개체로 존재 하는 경우에 프로젝트 해당 보기에 대 한 문서 데이터 개체를 사용할 수 있는지 여부를 확인 해야 합니다. 문서 데이터 개체로 호환 이면 완료 단계에서 설명한 [프로젝트 관련 편집기를 열고](../extensibility/how-to-open-project-specific-editors.md)합니다.  
  
     문서 데이터 개체로 호환 되지 않는 경우 오류가 발생 하는 파일이 현재 사용 중인 나타내는 사용자에 게 표시 됩니다. 이 오류만 표시할지 일시적인 경우에는 사용자가 아닌 다른 편집기를 사용 하 여 파일을 열고 하려는 파일을 동시에 컴파일되는 경우와 같은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코어 텍스트 편집기입니다. 코어 텍스트 편집기 컴파일러 문서 데이터 개체로 공유할 수 있습니다.  
  
3.  문서 데이터 개체나 문서 보기 개체에 있기 때문에 문서가 열려 있지 않은 경우의 단계를 완료 [프로젝트 관련 편집기를 열고](../extensibility/how-to-open-project-specific-editors.md)합니다.  
  
## <a name="opening-a-standard-editor"></a>표준 편집기 열기  
 이미 있는 파일에 대 한 표준 편집기를 열려면 다음 절차를 사용 하 여가 엽니다.  
  
#### <a name="to-open-a-standard-editor-for-an-open-file"></a>열려 있는 파일에 대 한 표준 편집기를 열려면  
  
1.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>를 호출합니다.  
  
     이 메서드는 먼저 문서 이미 열리지 않았는지를 호출 하 여 확인 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.IsDocumentOpen%2A>합니다. 문서가 이미 열려 있는, 해당 편집기 창 다시 표시 됩니다.  
  
2.  문서가 열려 있지 않으면 다음 단계에 따라 [하는 방법: 표준 편집기 열기](../extensibility/how-to-open-standard-editors.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [열기 및 프로젝트 항목 저장](../extensibility/internals/opening-and-saving-project-items.md)   
 [방법: 프로젝트 관련 편집기 열기](../extensibility/how-to-open-project-specific-editors.md)   
 [방법: 표준 편집기 열기](../extensibility/how-to-open-standard-editors.md)