---
title: "방법: MSBuild.exe를 사용하여 솔루션의 특정 대상 빌드 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, building specific targets in a solution
- msbuild.exe, building specific targets in a solution
- MSBuild, msbuild.exe
ms.assetid: f46feb9b-4c16-4fec-b6e1-36a959692ba3
caps.latest.revision: "10"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 3d683a5f8e8dd78e399fc0fadbc4cccf614013a3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-build-specific-targets-in-solutions-by-using-msbuildexe"></a>방법: MSBuild.exe를 사용하여 솔루션의 특정 대상 빌드
MSBuild.exe를 사용하여 솔루션에서 특정 프로젝트의 특정 대상을 빌드할 수 있습니다.  
  
### <a name="to-build-a-specific-target-of-a-specific-project-in-a-solution"></a>솔루션에서 특정 프로젝트의 특정 대상을 빌드하려면  
  
1.  명령줄에서 `MSBuild.exe <SolutionName>.sln`을 입력합니다. 여기서 `<SolutionName>`은 실행할 대상이 포함된 솔루션의 파일 이름에 해당합니다.  
  
2.  **/t** 스위치 뒤에 대상을 *ProjectName*:*TargetName* 형식으로 지정합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `NotInSlnFolder` 프로젝트의 `Rebuild` 대상을 실행하고 나서 `NewFolder` 솔루션 폴더에 있는 `InSolutionFolder` 프로젝트의 `Clean` 대상을 실행합니다.  
  
```  
msbuild SlnFolders.sln /t:NotInSlnfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>참고 항목  
 [명령줄 참조](../msbuild/msbuild-command-line-reference.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [MSBuild](../msbuild/msbuild.md)  
 [MSBuild 개념](../msbuild/msbuild-concepts.md)