---
title: "연습: 편집기 확장에서 DTE 개체를 액세스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 새-DTE 개체를 가져오는 중"
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
caps.latest.revision: 22
caps.handback.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
---
# 연습: 편집기 확장에서 DTE 개체를 액세스
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Vspackage를 호출 하 여 DTE 개체를 가져올 수는 <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> DTE 개체의 형식 사용 하 여 메서드. 프레임 워크 MEF \(Managed Extensibility\) 확장에서 가져올 수 있습니다 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> 다음 호출에서 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> 형식의 메서드 <xref:EnvDTE.DTE>합니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## DTE 개체를 가져오는 중  
  
#### ServiceProvider에서 DTE 개체를 가져와  
  
1.  라는 C\# VSIX 프로젝트를 만듭니다 `DTETest`합니다. 편집기 분류자 항목 템플릿을 추가 하 고 이름을 `DTETest`합니다. 자세한 내용은 [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)을 참조하세요.  
  
2.  프로젝트에 다음 어셈블리 참조를 추가 합니다.  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  DTETest.cs 파일을 이동한 다음 추가 `using` 지시문:  
  
    ```c#  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  에 `GetDTEProvider` 클래스, 가져오기는 <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>합니다.  
  
    ```c#  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  `GetClassifier()` 메서드에 다음 코드를 추가합니다.  
  
    ```c#  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  사용 해야 하는 경우는 <xref:EnvDTE80.DTE2> 인터페이스를 DTE 개체를 캐스팅할 수 있습니다.  
  
## 참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)