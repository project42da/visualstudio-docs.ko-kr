---
title: "작업 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 작업 만들기"
  - "MSBuild, 작업 작성"
  - "작업, MSBuild용으로 만들기"
ms.assetid: 3ebc5f87-8f00-46fc-82a1-228f35a6823b
caps.latest.revision: 19
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 19
---
# 작업 작성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

작업은 빌드 프로세스를 진행하는 동안 실행되는 코드를 제공합니다.  작업은 대상에 포함되어 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에는 일반 작업 라이브러리가 포함되어 있습니다. 이러한 일반 작업 외에도 사용자가 직접 작업을 만들 수도 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에 포함되어 있는 작업 라이브러리에 대한 자세한 내용은 [Task Reference](../msbuild/msbuild-task-reference.md)를 참조하십시오.  
  
## 작업  
 작업의 예로는 하나 이상의 파일을 복사하는 [Copy](../msbuild/copy-task.md), 디렉터리를 만드는 [MakeDir](../msbuild/makedir-task.md), [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 소스 코드 파일을 컴파일하는 [Csc](../msbuild/csc-task.md) 등이 있습니다.  각 작업은 Microsoft.Build.Framework.dll 어셈블리에 정의되어 있는 <xref:Microsoft.Build.Framework.ITask> 인터페이스를 구현하는 .NET 클래스로 구현됩니다.  
  
 다음 두 가지 방법을 사용하여 작업을 구현할 수 있습니다.  
  
-   <xref:Microsoft.Build.Framework.ITask> 인터페이스를 직접 구현합니다.  
  
-   Microsoft.Build.Utilities.dll 어셈블리에 정의되어 있는 <xref:Microsoft.Build.Utilities.Task> 도우미 클래스에서 클래스를 파생시킵니다.  작업에서는 ITask를 구현하고 일부 ITask 멤버의 기본 구현을 제공합니다.  또한 로깅이 더 쉽습니다.  
  
 두 경우 모두 작업이 실행될 때 호출되는 메서드인 `Execute` 메서드를 클래스에 추가해야 합니다.  이 메서드는 매개 변수를 사용하지 않으며 `Boolean` 값을 반환합니다. 즉, 작업이 성공하면 `true`를 반환하고, 실패하면 `false`를 반환합니다.  다음 예제에서는 작업을 수행하지 않고 `true`를 반환하는 작업을 보여 줍니다.  
  
```  
using System;  
using Microsoft.Build.Framework;  
using Microsoft.Build.Utilities;  
  
namespace MyTasks  
{  
    public class SimpleTask : Task  
    {  
        public override bool Execute()  
        {  
            return true;  
        }  
    }  
}  
```  
  
 다음 프로젝트 파일에서 이 작업을 실행합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <Target Name="MyTarget">  
        <SimpleTask />  
    </Target>  
</Project>  
```  
  
 작업 클래스에서 .NET 속성을 만들면 작업이 실행될 때 프로젝트 파일에서 입력을 받을 수도 있습니다.  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 작업의  `Execute` 메서드를 호출하기 바로 전에 이러한 속성을 설정합니다.  문자열 속성을 만들려면 다음과 같은 작업 코드를 사용합니다.  
  
```  
using System;  
using Microsoft.Build.Framework;  
using Microsoft.Build.Utilities;  
  
namespace MyTasks  
{  
    public class SimpleTask : Task  
    {  
        public override bool Execute()  
        {  
            return true;  
         }  
  
        private string myProperty;  
        public string MyProperty  
        {  
            get { return myProperty; }  
            set { myProperty = value; }  
        }  
    }  
}  
```  
  
 다음 프로젝트 파일은 이 작업을 실행하고 `MyProperty`를 지정된 값으로 설정합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
   <Target Name="MyTarget">  
      <SimpleTask MyProperty="Value for MyProperty" />  
   </Target>  
</Project>  
```  
  
## 작업 등록  
 프로젝트에서 작업을 실행하려면 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 작업 클래스를 포함하는 어셈블리를 찾는 방법을 알아야 합니다.  작업은 [UsingTask Element \(MSBuild\)](../msbuild/usingtask-element-msbuild.md)를 사용하여 등록됩니다.  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 파일인 Microsoft.Common.Tasks는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 제공하는 모든 작업을 등록하는 `UsingTask` 요소 목록이 포함되어 있는 프로젝트 파일입니다.  이 파일은 모든 프로젝트를 빌드할 때 자동으로 포함됩니다.  Microsoft.Common.Tasks에 등록된 작업이 현재 프로젝트 파일에도 등록된 경우 현재 프로젝트 파일이 우선합니다. 즉, 기본 작업을 같은 이름의 사용자 작업으로 재정의할 수 있습니다.  
  
> [!TIP]
>  [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 제공하는 작업 목록은 Microsoft.Common.Tasks의 내용을 보면 알 수 있습니다.  
  
## 작업에서 이벤트 발생시키기  
 <xref:Microsoft.Build.Utilities.Task> 도우미 클래스에서 파생된 작업의 경우 <xref:Microsoft.Build.Utilities.Task> 클래스의 다음 도우미 메서드를 사용하면 등록된 로거에서 catch하고 표시할 이벤트를 발생시킬 수 있습니다.  
  
```  
public override bool Execute()  
{  
    Log.LogError("messageResource1", "1", "2", "3");  
    Log.LogWarning("messageResource2");  
    Log.LogMessage(MessageImportance.High, "messageResource3");  
    ...  
}  
```  
  
 작업에서 <xref:Microsoft.Build.Framework.ITask>를 직접 구현하는 경우에도 사용자는 계속 그러한 이벤트를 발생시킬 수 있지만 IBuildEngine 인터페이스를 사용해야 합니다.  다음 예제에서는 ITask를 구현하고 사용자 지정 이벤트를 발생시키는 작업을 보여 줍니다.  
  
```  
public class SimpleTask : ITask  
{  
    private IBuildEngine buildEngine;  
    public IBuildEngine BuildEngine  
    {  
        get{ return buildEngine; }  
        set{ buildEngine = value; }  
    }  
  
    public override bool Execute()  
    {  
        TaskEventArgs taskEvent =  
            new TaskEventArgs(BuildEventCategory.Custom,  
            BuildEventImportance.High, "Important Message",  
           "SimpleTask");  
        BuildEngine.LogBuildEvent(taskEvent);  
        return true;  
    }  
}  
```  
  
## 작업 매개 변수 설정 요구  
 특정 작업 속성을 "필수"로 표시하여 작업을 실행하는 모든 프로젝트 파일에서 이러한 속성에 대해 값을 반드시 설정하도록 하고, 그렇지 않으면 빌드가 실패하도록 할 수 있습니다.  `[Required]` 특성을 다음과 같이 작업의 .NET 속성에 적용합니다.  
  
```  
private string requiredProperty;  
  
[Required]  
public string RequiredProperty  
{  
    get { return requiredProperty; }  
    set { requiredProperty = value; }  
}  
```  
  
 `[Required]` 특성은 <xref:Microsoft.Build.Framework> 네임스페이스의 <xref:Microsoft.Build.Framework.RequiredAttribute>에 의해 정의됩니다.  
  
## 예제  
  
### 설명  
 다음 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스에서는 <xref:Microsoft.Build.Utilities.Task> 도우미 클래스에서 파생되는 작업을 보여 줍니다.  이 작업은 성공을 나타내는 `true`를 반환합니다.  
  
### 코드  
  
```  
using System;  
using Microsoft.Build.Utilities;  
  
namespace SimpleTask1  
{  
    public class SimpleTask1: Task  
    {  
        public override bool Execute()  
        {  
            // This is where the task would presumably do its work.  
            return true;  
        }  
    }  
}  
```  
  
## 예제  
  
### 설명  
 다음 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스에서는 <xref:Microsoft.Build.Framework.ITask> 인터페이스를 구현하는 작업을 보여 줍니다.  이 작업은 성공을 나타내는 `true`를 반환합니다.  
  
### 코드  
  
```  
using System;  
using Microsoft.Build.Framework;  
  
namespace SimpleTask2  
{  
    public class SimpleTask2: ITask  
    {  
        //When implementing the ITask interface, it is necessary to  
        //implement a BuildEngine property of type  
        //Microsoft.Build.Framework.IBuildEngine. This is done for  
        //you if you derive from the Task class.  
        private IBuildEngine buildEngine;  
        public IBuildEngine BuildEngine  
        {  
            get  
            {  
                return buildEngine;  
            }  
            set  
            {  
                buildEngine = value;  
            }  
         }  
  
        // When implementing the ITask interface, it is necessary to  
        // implement a HostObject property of type Object.  
        // This is done for you if you derive from the Task class.  
        private Object hostObject;  
        public Object HostObject  
        {  
            get  
            {  
                return hostObject;  
            }  
  
            set  
            {  
                hostObject = value;  
            }  
        }  
  
        public bool Execute()  
        {  
            // This is where the task would presumably do its work.  
            return true;  
        }  
    }  
}  
```  
  
## 예제  
  
### 설명  
 다음 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 클래스에서는 <xref:Microsoft.Build.Utilities.Task> 도우미 클래스에서 파생되는 작업을 보여 줍니다.  이 작업에는 필수 문자열 속성이 있으며 모든 등록된 로거에서 표시하는 이벤트를 발생시킵니다.  
  
### 코드  
 [!code-cs[msbuild_SimpleTask3#1](../msbuild/codesnippet/CSharp/task-writing_1.cs)]  
  
## 예제  
  
### 설명  
 다음 예제에서는 앞의 예제 작업인 SimpleTask3을 호출하는 프로젝트 파일을 보여 줍니다.  
  
### 코드  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <UsingTask TaskName="SimpleTask3.SimpleTask3"   
        AssemblyFile="SimpleTask3\bin\debug\simpletask3.dll"/>  
  
    <Target Name="MyTarget">  
        <SimpleTask3 MyProperty="Hello!"/>  
    </Target>  
</Project>  
```  
  
## 참고 항목  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [Task Reference](../msbuild/msbuild-task-reference.md)