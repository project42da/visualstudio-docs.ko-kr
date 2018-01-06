---
title: "연습: 편집기 확장에서 DTE 개체 액세스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: af14fa5f9a76e08a1fba3355e9391ce8229bd652
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>연습: 편집기 확장에서 DTE 개체 액세스
Vspackage에서 호출 하 여 DTE 개체를 가져올 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> 메서드 DTE 개체 유형 사용 합니다. 프레임 워크 MEF (Managed Extensibility) 확장에서 가져올 수 있습니다 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> 다음 호출에서 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> 형식의 메서드 <xref:EnvDTE.DTE>합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="getting-the-dte-object"></a>DTE 개체를 가져오는 중  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>ServiceProvider에서 DTE 개체를 가져오려면  
  
1.  라는 C# VSIX 프로젝트 `DTETest`합니다. 편집기 분류자 항목 템플릿을 추가 하 고 이름을 `DTETest`합니다. 자세한 내용은 참조 [편집기 항목 템플릿을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-an-editor-item-template.md)합니다.  
  
2.  프로젝트에 다음 어셈블리 참조를 추가 합니다.  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  DTETest.cs 파일을 이동한 다음 추가 `using` 지시문:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  에 `GetDTEProvider` 클래스, 가져오기는 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>합니다.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  `GetClassifier()` 메서드에 다음 코드를 추가합니다.  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  사용 해야 하는 경우는 <xref:EnvDTE80.DTE2> 인터페이스를 DTE 개체를 캐스팅할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)