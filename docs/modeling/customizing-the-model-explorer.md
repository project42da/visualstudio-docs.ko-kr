---
title: "모델 탐색기 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.explorerbehavior
helpviewer_keywords:
- Domain-Specific Language Tools, Domain-Specific Language Explorer
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: eac91df1a07e54b80e88538695b1cc22353396d6
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="customizing-the-model-explorer"></a>모델 탐색기 사용자 지정
변경할 수 있습니다 모양 및 동작 탐색기의 도메인 특정 언어 디자이너에 대 한 다음과 같습니다.  
  
-   창 제목을 변경 합니다.  
  
-   탭 아이콘을 변경 합니다.  
  
-   노드에 대 한 아이콘을 바꿉니다.  
  
-   노드를 숨깁니다.  
  
## <a name="changing-the-window-title"></a>창 제목 변경  
 생성 된 탐색기의 창 제목을 변경 하려면 선택 **탐색기 동작** 에 **DSL 탐색기**, 한 다음는 **속성** 창에서 설정 된  **제목** 속성을 원하는 제목입니다.  
  
## <a name="changing-the-tab-icon"></a>탭 아이콘 변경  
 탐색기 탭 아이콘을 변경 하려면.bmp 파일에서 16 x 16 픽셀 아이콘을 사용 합니다. 아이콘 파일 \DslPackage\Resources\ 폴더에 저장 한 다음에 파일 이름을 변경 **ModelExplorerToolWindowBitmaps.bmp**합니다. 예를 들어 변경할 수 있습니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] setup.ico 아이콘.bmp 형식으로 파일 및 파일 이름을 **DSLLanguageName\DslPackage\Resources\ModelExplorerToolWindowBitmaps.bmp**합니다. 와 함께 도킹 한 경우 생성 된 디자이너 탐색기 탭에이 아이콘이 표시 됩니다 **솔루션 탐색기**합니다.  
  
## <a name="setting-custom-icons-on-explorer-nodes"></a>탐색기 노드에서 사용자 지정 아이콘 설정  
 탐색기에서 탐색기 노드 설정을 사용 하 여 노드를 사용자 지정할 수 있습니다. 다음 절차에는 노드에 아이콘을 추가 하는 방법을 보여 줍니다.  
  
#### <a name="to-add-an-icon-to-an-explorer-node"></a>아이콘 탐색기 노드를 추가 하려면  
  
1.  만들기는 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 솔루션 작업 흐름 템플릿을 사용 하 여 솔루션입니다.  
  
2.  .Bmp 파일에 16 x 16 픽셀 아이콘을 포함 하는 **Dsl\Resources** 솔루션에 있는 폴더입니다.  
  
3.  에 **DSL 탐색기**를 마우스 오른쪽 단추로 클릭 **탐색기 동작** 클릭 하 고 **새 탐색기 노드 설정 추가**합니다.  
  
     **ExplorerNodeSettings** 노드가 아래에 표시 된 **사용자 지정 노드 설정** 노드.  
  
4.  선택 **ExplorerNodeSettings**, 한 다음는 **속성** 창의 설정 **클래스** 를 **행위자**합니다.  
  
5.  설정 **아이콘을 표시** 아이콘 파일의 경로입니다.  
  
6.  모든 템플릿 변환 빌드 및 솔루션을 실행 합니다.  
  
7.  생성 된 디자이너에서 예제 다이어그램을 엽니다.  
  
     탐색기에서 세 개의 표시할지 **행위자** 프로그램 아이콘에 있는 노드.  
  
> [!NOTE]
>  생성 된 탐색기에 표시 되는 모든 요소에 대 한 노드 아이콘을 설정한 경우 모든 탐색기 노드에 아이콘이 표시 됩니다. 아이콘이 없는 설정 된 경우 노드는 기본 아이콘이 표시 됩니다.  
  
## <a name="changing-the-name-displayed-on-an-explorer-node"></a>탐색기 노드에 표시 되는 이름을 변경 합니다.  
 탐색기에서 모델 요소의 이름이 표시 되는 방식을 변경할 수 있습니다. 다음 절차의 이름을 표시 하는 방법을 보여 줍니다는 **작업** 에서 참조 하는 **주석** 주석 노드에서.  
  
#### <a name="to-display-a-property"></a>속성을 표시 하려면  
  
1.  이전 절차에서 만든 솔루션을 엽니다.  
  
2.  다음 사항을 확인는 **주석** 속성 이름 가진 role의 복합성을 설정 하 여 단일 도메인 클래스만 참조 **주제** 을 0..1 합니다. 속성 이름을 잘 **주체**, 관계 이름 잘 및 **CommentReferencesSubject**합니다.  
  
3.  에 **DSL 탐색기**를 마우스 오른쪽 단추로 클릭 **탐색기 동작** 클릭 하 고 **새 탐색기 노드 설정 추가**합니다.  
  
     **ExplorerNodeSettings** 노드가 아래에 표시 된 **사용자 지정 노드 설정** 노드.  
  
4.  선택 **ExplorerNodeSettings**, 한 다음는 **속성** 창의 설정 **클래스** 를 **주석**합니다.  
  
5.  마우스 오른쪽 단추로 클릭는 **주석** 노드를 차례로 클릭 한 다음 **새 속성 경로 추가**합니다.  
  
     이라는 새 노드가 나타납니다 **속성은 표시**합니다.  
  
6.  선택 **속성은 표시**, 한 다음는 **속성** 창의 값 필드를 클릭 **속성 경로**합니다. 선택 **주석**, 다음 **CommentReferencesSubject**, 다음 **FlowElement**합니다. 결과 경로 유사 해야 **CommentReferencesSubject.Subject/! 제목**합니다.  
  
7.  값 필드에 **속성**선택, **이름**합니다.  
  
8.  모든 템플릿 변환 빌드 및 솔루션을 실행 합니다.  
  
9. 생성 된 디자이너에서 예제 다이어그램을 엽니다.  
  
10. 그리기는 **주석 커넥터** 주석 요소 사이 **Task1** 다이어그램의 요소입니다.  
  
     탐색기 노드를 주석으로 표시할지 **Task1**합니다.  
  
## <a name="hiding-nodes"></a>숨김 노드  
 탐색기에서 해당 경로를 추가 하 여 노드를 숨길 수는 **숨겨진 노드** 의 노드는 **DSL 탐색기**합니다. 다음 절차에서는 숨기는 방법을 보여 줍니다. **주석** 노드.  
  
#### <a name="to-hide-an-explorer-node"></a>탐색기 노드를 숨기려면  
  
1.  이전 절차에서 만든 솔루션을 엽니다.  
  
2.  에 **DSL 탐색기**를 마우스 오른쪽 단추로 클릭 **탐색기 동작** 클릭 하 고 **새 도메인 경로 추가**합니다.  
  
     A **도메인 경로** 노드 아래에 나타납니다 **숨겨진 노드**합니다.  
  
3.  선택 **도메인 경로**, 한 다음는 **속성** 창의 값 필드를 클릭 **경로 정의**합니다. 선택 **FlowGraph**, 다음 **FlowGraphHasComments**합니다. 결과 경로 유사 해야 **FlowGraphHasComments.Comments**  
  
4.  모든 템플릿 변환 빌드 및 솔루션을 실행 합니다.  
  
5.  생성 된 디자이너에서 예제 다이어그램을 엽니다.  
  
     탐색기만 표시 됩니다는 **행위자** 노드를 표시 하지 않아야 하 고는 **주석** 노드.  
  
## <a name="see-also"></a>참고 항목

[도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)