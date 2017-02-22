---
title: "등록 하는 도구 창 | Microsoft Docs"
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
  - "도구 창 관리 등록"
  - "도구 창에 등록"
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 등록 하는 도구 창
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

도구 창을 사용 하 여 등록할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 및  <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>  
  
## 예제  
  
```c#  
  
      [ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")] [ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)] [ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]  
[ProvideMenuResource(1000, 1)]  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]  
public class PackageToolWindow : Package  
{  
```  
  
 위의 코드에는 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> PersistedWindowPane DynamicWindowPane 도구 창은 Visual Studio와 함께 등록 합니다. 지속형된 도구 창 도킹 이며와 탭 **솔루션 탐색기**, 동적 창 위치와 크기를 시작 하는 기본 제공 됩니다. 동적 창이 이루어집니다 일시적인 시작 시에 생성 되지 않도록 나타냅니다. 이 시스템 레지스트리에서 ToolWindows에 DontForceCreate 값을 씁니다. 자세한 내용은 [도구 창 표시 구성](../extensibility/tool-window-display-configuration.md)을 참조하세요.