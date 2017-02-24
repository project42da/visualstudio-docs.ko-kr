---
title: "방법: 작업의 오류 무시 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, ignoring errors
- ContinueOnError attribute [MSBuild]
ms.assetid: e2f1ca4f-787b-44bd-bc64-81a036025e96
caps.latest.revision: 18
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 3ba7680d46345f2b49019659c715cfb418933d39
ms.openlocfilehash: 263a2cdc87b46a70d9114a830955a54cde85d527

---
# <a name="how-to-ignore-errors-in-tasks"></a>방법: 작업의 오류 무시
경우에 따라 빌드에서 특정 작업의 폴트 발생을 허용하고자 합니다. 중요하지 않은 작업이 실패할 경우 필요한 출력이 계속 생성될 수 있으므로 빌드를 계속 진행하고자 합니다. 예를 들어 각 구성 요소가 빌드된 후 프로젝트에서 `SendMail` 작업을 사용하여 전자 메일 메시지를 보낸다면 메일 서버를 사용할 수 없고 상태 메시지를 보낼 수 없는 경우에도 완료될 때까지 빌드를 진행하도록 허용할 수 있습니다. 또는 예를 들어 일반적으로 빌드 중에 중간 파일이 삭제된다면 해당 파일을 삭제할 수 없는 경우에도 완료될 때까지 빌드를 진행하도록 허용할 수 있습니다.  
  
## <a name="using-the-continueonerror-attribute"></a>ContinueOnError 특성 사용  
 `Task` 요소의 `ContinueOnError` 특성은 작업 실패가 발생할 경우 빌드를 중지하거나 계속할지 여부를 제어합니다. 이 특성은 빌드를 계속할 경우 오류를 오류 또는 경고로 처리할지 여부를 제어합니다.  
  
 `ContinueOnError` 특성은 다음 값 중 하나를 포함할 수 있습니다.  
  
-   **WarnAndContinue** 또는 **true**. 작업이 실패할 경우 [Target](../msbuild/target-element-msbuild.md) 요소의 후속 작업과 빌드가 계속 실행되고 작업에서 발생한 모든 오류가 경고로 처리됩니다.  
  
-   **ErrorAndContinue**. 작업이 실패할 경우 `Target` 요소의 후속 작업과 빌드가 계속 실행되고 작업에서 발생한 모든 오류가 오류로 처리됩니다.  
  
-   **ErrorAndStop** 또는 **false**(기본값). 작업이 실패할 경우 `Target` 요소의 나머지 작업이 실행되지 않고 전체 `Target` 요소와 빌드가 실패한 것으로 간주됩니다.  
  
 .NET Framework 4.5 이전 버전은 `true` 및 `false` 값만 지원합니다.  
  
 `ContinueOnError`의 기본값은 `ErrorAndStop`입니다. 특성을 `ErrorAndStop`으로 설정하면 프로젝트 파일을 읽는 모든 사용자에게 동작이 명시적으로 제시됩니다.  
  
#### <a name="to-ignore-an-error-in-a-task"></a>작업의 오류를 무시하려면  
  
-   작업의 `ContinueOnError` 특성을 사용합니다. 예:  
  
     `<Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>`  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Delete` 작업이 실패하더라도 `Build` 대상이 계속 실행되고 빌드가 성공한 것으로 간주됨을 보여 줍니다.  
  
```xml  
<Project DefaultTargets="FakeBuild"  
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Files Include="*.obj"/>  
    </ItemGroup>  
    <Target Name="Clean">  
        <Delete Files="@(Files)" ContinueOnError="WarnAndContinue"/>  
    </Target>  
  
    <Target Name="FakeBuild" DependsOnTargets="Clean">  
        <Message Text="Building after cleaning..."/>  
    </Target>  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목
[MSBuild](../msbuild/msbuild.md)  
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [작업](../msbuild/msbuild-tasks.md)


<!--HONumber=Feb17_HO4-->


