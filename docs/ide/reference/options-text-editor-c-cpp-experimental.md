---
title: "옵션, 텍스트 편집기, C/C++, 실험적 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.C/C++.Experimental
- VS.ToolsOptionsPages.Text_Editor.C%2FC%2B%2B.Experimental
- VS.ToolsOptionsPages.Text_Editor.C\C++.Experimental
ms.assetid: b9e9dda2-350c-460d-b368-37d6c5342eee
caps.latest.revision: 10
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
ms.sourcegitcommit: 47c39bd711b69efdb863d71f11e3e472054a3ce3
ms.openlocfilehash: 889d538b732b360b475788ec6d67b47920703c73
ms.lasthandoff: 04/06/2017

---
# <a name="options-text-editor-cc-experimental"></a>옵션, 텍스트 편집기, C/C++, 실험적
이러한 옵션을 변경하면 C 또는 C++에서 프로그래밍할 때 IntelliSense 및 검색 데이터베이스 관련 동작을 변경할 수 있습니다. 이러한 기능은 실험적이며 향후 릴리스의 Visual Studio에서 수정되거나 제거될 수 있습니다. 이 항목에서는 Visual Studio 2017의 옵션을 설명합니다. Visual Studio 2015의 경우 [옵션, 텍스트 편집기, C/C++, 실험적](https://msdn.microsoft.com/library/mt591979.aspx)을 참조하세요. 
  
 이 속성 페이지에 액세스하려면 **Ctrl+Q**를 눌러 `Quick Launch`를 활성화한 다음 "실험적"을 입력합니다. 빠른 실행에서 처음 몇 글자 페이지 다음의 페이지를 찾습니다. **도구 | 옵션**을 선택하고 **텍스트 편집기**, **C/C++**를 차례로 확장한 다음 **실험적**을 선택하여 액세스할 수도 있습니다.  

 이러한 기능은 Visual Studio 2017 설치에서 사용할 수 있습니다.  
  
> [!NOTE]
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="enable-predictive-intellisense"></a>예측 IntelliSense 사용
예측 IntelliSense는 컨텍스트와 관련이 있는 결과만 표시되도록 IntelliSense 드롭다운 목록에 표시되는 결과의 수를 제한합니다. 예를 들어 <code>int x =</code>을 입력하고 IntelliSense 드롭다운을 호출하면 정수 또는 정수를 반환하는 함수만 표시됩니다. 예측 IntelliSense는 기본적으로 꺼져 있습니다.

## <a name="enable-faster-project-load"></a>빠른 프로젝트 로드 사용
이 옵션을 사용하면 다음에 프로젝트를 열 때 Visual Studio에서 프로젝트 데이터를 캐시할 수 있으며, 프로젝트 파일에서 다시 계산하지 않고 캐시한 데이터를 로드할 수 있습니다. 캐시한 데이터를 사용하면 프로젝트 로드 시간이 상당히 빨라집니다.  

## <a name="additional-features-in-the-visual-studio-gallery"></a>Visual Studio 갤러리의 추가 기능
Visual Studio 갤러리의 추가 텍스트 편집기 기능은 [여기](http://go.microsoft.com/fwlink/?LinkId=692016)에서 목록을 참조하세요. 예제는 [C++ 빠른 조치 방법](https://visualstudiogallery.msdn.microsoft.com/be91feef-8dc3-4f7a-ac9f-f34e7ca5918f)(영문)이며, 다음을 지원합니다.  
  
-   **누락된 #include 추가** - 코드의 알 수 없는 기호에 대해 관련 #include를 제안합니다.  
  
-   **네임스페이스/정규화 기호를 사용하여 추가** - 네임스페이스를 제외하고 이전 항목과 유사합니다.  
  
-   **누락된 세미콜론 추가**  
  
-   **MSDN 도움말** - MSDN에서 오류 메시지를 검색합니다.  
  
 물결선을 가리켜서 전구를 표시하거나 기본 바로 가기 키 Ctrl+.(Ctrl+점)을 사용할 수 있습니다. 바로 가기 키의 경우 특정 오류나 토큰에 캐럿을 배치할 필요가 없으며 오류와 같은 줄에 있기만 하면 해당 줄의 모든 항목에 대한 제안을 호출할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어별 편집기 옵션 설정](../../ide/reference/setting-language-specific-editor-options.md)   
 [C++에서의 리팩터링(VC 블로그)](http://blogs.msdn.com/b/vcblog/archive/2014/11/14/all-about-c-refactoring-in-visual-studio-2015-preview.aspx)
