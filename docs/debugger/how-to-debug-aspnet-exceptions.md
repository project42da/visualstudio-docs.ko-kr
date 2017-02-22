---
title: "방법: ASP.NET 예외 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ASP.NET, 예외"
  - "디버깅[Visual Studio], ASP.NET 예외"
  - "예외, ASP.NET"
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: 23
caps.handback.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: ASP.NET 예외 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

예외 디버깅은 강력한 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 개발하는 데 중요한 요소입니다.  예외를 디버깅하는 방법에 대한 일반적인 내용은 [디버거를 사용한 예외 관리](../debugger/managing-exceptions-with-the-debugger.md)를 참조하십시오.  
  
 처리되지 않은 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 예외를 디버깅하려면 처리되지 않은 예외가 발생할 때 디버거에서 실행을 중지하도록 해야 합니다.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 런타임에는 최상위 예외 처리기가 있습니다.  따라서 디버거는 처리되지 않은 예외에서 기본적으로 중단되지 않습니다.  예외가 throw될 때 디버거에서 실행을 중단하도록 지정하려면 **예외** 대화 상자에서 특정 예외에 대해 **다음 예외가 발생할 경우 중단: Throw됨** 설정을 선택해야 합니다.  
  
 내 코드만 옵션을 설정한 경우 **다음 예외가 발생할 경우 중단: Throw됨**을 사용하면 .NET Framework 메서드 또는 다른 시스템 코드에서 예외가 throw되는 즉시 디버거에서 실행을 중단하지 않습니다.  이러한 경우 디버거의 실행은 비시스템 코드를 적중해야 중단됩니다.  그러므로 예외가 발생할 때 시스템 코드를 단계별로 수행할 필요가 없습니다.  
  
 내 코드만 옵션을 사용할 경우 더 유용한 다른 옵션\(**다음 예외가 발생할 경우 중단: 사용자가 처리하지 않음**\)도 사용할 수 있습니다.  예외에 대해 이 설정을 선택하면 디버거는 사용자 코드에서 예외를 catch하여 처리하지 않는 경우에 한해서만 사용자 코드에서 실행을 중단합니다.  이렇게 설정할 경우 최상위 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 예외 처리기가 사용자가 작성하지 않은 코드에 있기 때문에 해당 처리기의 결과가 무시됩니다.  
  
### 내 코드만 옵션을 사용하여 ASP.NET 예외 디버깅을 설정하려면  
  
1.  **디버그** 메뉴에서 **예외**를 클릭합니다.  
  
     **예외** 대화 상자가 표시됩니다.  
  
2.  **Common Language Runtime Exceptions** 행에서 **Throw됨** 또는 **사용자가 처리하지 않음**을 선택합니다.  
  
     **사용자가 처리하지 않음** 설정을 사용하려면 **내 코드만**을 설정해야 합니다.  
  
### 최상의 방법으로 ASP.NET 예외 처리를 수행하려면  
  
-   예측 가능하며 처리 방법을 알고 있는 예외를 throw할 수 있는 코드의 바깥쪽에 `try … catch` 블록을 배치합니다.  예를 들어, 응용 프로그램에서 XML Web services를 호출하거나 SQL Server를 직접 호출할 경우에는 다양한 예외가 발생할 수 있으므로 해당 코드는 **try … catch** 블록에 있어야 합니다.