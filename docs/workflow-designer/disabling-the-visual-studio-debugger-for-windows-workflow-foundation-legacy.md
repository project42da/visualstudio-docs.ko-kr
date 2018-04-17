---
title: Windows Workflow Foundation (레거시)에 대 한 Visual Studio 디버거 사용 안 함 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- workflows, disabling debugger
- debugging workflows, disabling debugger
- workflow debugger, disabling
ms.assetid: 9da96d0e-f941-4fa9-a1a5-6bab50adfec9
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a609062f3f84538f7c1655cd5ca82971fc608f62
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Visual Studio Debugger for Windows Workflow Foundation을 사용하지 않도록 설정(레거시)

이 항목에서는 사용 하지 않도록 설정 하는 방법을 설명는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 빌드할 때 구성 파일을 사용 하 여 디버거 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 레거시 Windows 워크플로 디자이너에서 응용 프로그램입니다. 레거시 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]는 [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] 또는 [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)]를 대상으로 해야 하는 경우에 사용합니다.

 기본적으로는 호스트 프로세스에 [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)]용 [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] 디버거를 사용할 수 있습니다. 워크플로 디버깅을 사용 하지 않으려면 하면 명시적으로 해제 해야 "DisableWorkflowDebugging" 항목을 추가 하 여  **\<스위치 >** 요소에는  **\<system.diagnostics >**호스트 구성 파일의 섹션입니다.

 다음 예제에서는 워크플로 디버깅을 사용하지 않도록 호스트 구성 파일을 수정하는 방법을 보여 줍니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
   <system.diagnostics>
      <switches>
         <add name="DisableWorkflowDebugging" value="true"/>
      </switches>
   </system.diagnostics>
</configuration>
```

## <a name="see-also"></a>참고자료

- [Visual Studio Debugger for Windows Workflow Foundation 호출(레거시)](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)
- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)