---
title: "방법: 빌드 출력 디렉터리 변경 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: 14
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 14be502abb42d6bb9637e7394ec8bf20b50c4231
ms.lasthandoff: 04/05/2017

---
# <a name="how-to-change-the-build-output-directory"></a>방법: 빌드 출력 디렉터리 변경
프로젝트에서 생성된 구성별로(디버그, 릴리스 또는 둘 다) 출력의 위치를 지정할 수 있습니다.  
  
> [!NOTE]
>  **설치** 프로젝트가 있는 경우 이 문서 끝의 참고 사항을 참조하세요.  
  
## <a name="changing-the-build-output-directory"></a>빌드 출력 디렉터리 변경  
  
#### <a name="to-change-the-build-output-directory"></a>빌드 출력 디렉터리를 변경하려면  
  
1.  메뉴 모음에서 **프로젝트**, *Appname* **속성**을 선택합니다. **솔루션 탐색기** 에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택할 수도 있습니다.  
  
2.  Visual Basic 프로젝트의 경우 **컴파일** 탭을 선택합니다. Visual C# 프로젝트의 경우 **빌드** 탭을 선택합니다. C++ 프로젝트 또는 JavaScript 프로젝트의 경우 **일반** 탭을 선택합니다.  
  
3.  맨 위의 구성 드롭다운에서 출력 파일 위치를 변경하려는 구성(디버그, 릴리스 또는 둘 다)을 선택합니다.  
  
     출력 경로 항목(Visual Basic의 경우**빌드 출력 경로** , Visual C++의 경우 **출력 디렉터리** , JavaScript 및 C#의 경우 **출력 경로** )을 찾습니다. 프로젝트 디렉터리를 기준으로 새 빌드 출력 디렉터리를 지정합니다.  
  
> [!NOTE]
>  설치 프로젝트의 **출력 파일 이름** 상자는 프로젝트 파일의 위치는 변경하지 않고 Setup.exe 파일의 위치만 변경합니다. 자세한 내용은 **배포 프로젝트 속성 대화 상자, 구성 속성, 빌드**를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 디자이너, 빌드 페이지(C#)](../ide/reference/build-page-project-designer-csharp.md)   
 [일반 속성 페이지(프로젝트)](/cpp/ide/general-property-page-project)   
 [컴파일 및 빌드](../ide/compiling-and-building-in-visual-studio.md)
