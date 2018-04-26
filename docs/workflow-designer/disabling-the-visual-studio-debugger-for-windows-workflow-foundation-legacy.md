---
title: Visual Studio Debugger for Windows Workflow Foundation (레거시)를 사용 하지 않도록 설정 하는 워크플로 디자이너-
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
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
ms.openlocfilehash: 473ee507e35f5ec5df902df64ee34326dcf90a2b
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="disabling-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Visual Studio Debugger for Windows Workflow Foundation을 사용하지 않도록 설정(레거시)

이 항목에서는 레거시 Windows 워크플로 디자이너에서 Windows WF (Workflow Foundation) 응용 프로그램을 빌드할 때 구성 파일을 사용 하 여 Visual Studio 디버거를 사용 하지 않도록 설정 하는 방법에 설명 합니다. WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

 기본적으로는 Visual Studio 디버거에 대 한 Windows WF (Workflow Foundation)는 호스트 프로세스에 사용 됩니다. 워크플로 디버깅을 사용 하지 않으려면 하면 명시적으로 해제 해야 "DisableWorkflowDebugging" 항목을 추가 하 여  **\<스위치 >** 요소에는  **\<system.diagnostics >** 호스트 구성 파일의 섹션입니다.

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