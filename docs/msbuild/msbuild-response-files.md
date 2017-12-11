---
title: "MSBuild 지시 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- response files, MSBuild
- MSBuild, response files
- MSBuild, .rsp files
- .rsp files
ms.assetid: 9f53987b-20ee-470a-ab62-fce997bb5e15
caps.latest.revision: "3"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: a9ceab64ec0009dd143f42e1b94538690780f1bb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-response-files"></a>MSBuild 지시 파일
지시(.rsp) 파일은 MSBuild.exe 명령줄 스위치를 포함하는 텍스트 파일입니다. 각 스위치가 별도 줄에 있거나 모든 스위치가 한 줄에 있을 수 있습니다. 주석 줄의 앞에 **#** 기호가 붙습니다. **@** 스위치는 다른 지시 파일을 MSBuild.exe에 전달하는 데 사용됩니다.  
  
 자동 지시 파일은 프로젝트를 빌드할 때 자동으로 MSBuild.exe에서 사용하는 특별한 .rsp 파일입니다. MSBuild.rsp라는 파일은 MSBuild.exe와 같은 디렉터리에 있어야 하고, 그렇지 않으면 찾을 수 없습니다. 이 파일을 편집하여 MSBuild.exe에 대한 기본 명령줄 스위치를 지정할 수 있습니다. 예를 들어 프로젝트를 빌드할 때마다 동일한 로거를 사용하는 경우 **/logger** 스위치를 MSBuild.rsp에 추가할 수 있습니다. 그러면 MSBuild.exe는 프로젝트가 빌드될 때마다 로거를 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [명령줄 참조](../msbuild/msbuild-command-line-reference.md)