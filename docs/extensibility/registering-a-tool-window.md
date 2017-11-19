---
title: "도구 창을 등록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 79a2d2f1e9dc130fc280ce61ec282f30e55024ae
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="registering-a-tool-window"></a>도구 창을 등록 하는 중
도구 창을 사용 하 여 등록할 수 있는 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 및<xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## <a name="example"></a>예제  
  
```csharp  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 위의 코드에는 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 도구 창 PersistedWindowPane 및 DynamicWindowPane Visual Studio와 함께 등록 합니다. 지속형된 도구 창을 도킹 이며와 탭 **솔루션 탐색기**, 기본 시작 위치 및 크기가 동적 창 지정 합니다. 시작 시에 생성 되지 않도록 나타냅니다 동적 창 일시적인 수행 됩니다. 이 시스템 레지스트리에 ToolWindows 키에 DontForceCreate 값을 씁니다. 자세한 내용은 참조 [도구 창 디스플레이 구성](../extensibility/tool-window-display-configuration.md)합니다.