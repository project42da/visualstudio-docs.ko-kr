---
title: "모델 탐색기 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.dsltools.dsldesigner.explorerbehavior"
helpviewer_keywords: 
  - "도메인별 언어 도구, 도메인별 언어 탐색기"
ms.assetid: d2926444-9408-41d8-a27e-3fd0c416f9ac
caps.latest.revision: 20
caps.handback.revision: 20
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 모델 탐색기 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

하면 모양과 동작 탐색기의 도메인 관련 언어 디자이너에 대 한 다음과 같은 방법으로 변경할 수 있습니다.  
  
-   창 제목을 변경 합니다.  
  
-   탭 아이콘을 변경 합니다.  
  
-   노드에 대 한 아이콘을 변경 합니다.  
  
-   노드를 숨깁니다.  
  
## 창 제목 변경  
 생성 된 explorer 창 제목을 변경 하려면 선택  **Explorer 동작** 에  **DSL 탐색기**, 다음에  **속성** 창 설정의  **제목** 속성에 원하는 제목.  
  
## 탭 아이콘 변경  
 탐색기에 대 한 탭 아이콘을 변경 하려면.bmp 파일의 크기가 16 x 16 픽셀 아이콘을 사용 합니다.  아이콘 파일은 \\DslPackage\\Resources\\ 폴더에 저장 한 다음 파일 이름을 Modelexplorertoolwindowbitmaps.bmp으로 변경 합니다.  예를 들어, 변경할 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] setup.ico 아이콘 파일을.bmp 형식 및 Dsllanguagename\\dslpackage\\resources\\modelexplorertoolwindowbitmaps.bmp를 이름을 바꿉니다.  함께 도킹 되어 있을 때 생성 된 디자이너가이 아이콘을 탐색기 탭에서 표시 합니다  **솔루션 탐색기**.  
  
## 사용자 지정 아이콘을 탐색기 노드 설정  
 탐색기 노드 설정을 사용 하 여 노드를 탐색기에서 사용자 지정할 수 있습니다.  다음은 노드에 아이콘을 추가 하는 방법을 보여 줍니다.  
  
#### 탐색기 노드에 아이콘을 추가 하려면  
  
1.  작성 된 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 작업 흐름 솔루션 템플릿을 사용 하 여 솔루션입니다.  
  
2.  에 16 x 16 픽셀 아이콘이 포함 되어 있는.bmp 파일을 배치는  **Dsl\\Resources** 솔루션에서 폴더입니다.  
  
3.  에  **DSL 탐색기**, 마우스 오른쪽 단추로  **탐색기 문제** 하 고 다음을 클릭  **새 탐색기 노드 설정 추가**.  
  
     **ExplorerNodeSettings** 노드 아래에 나타납니다에  **사용자 지정 노드 설정** 노드.  
  
4.  선택  **ExplorerNodeSettings**, 다음에  **속성** 창 설정  **클래스** 에  **배우**.  
  
5.  설정  **아이콘 표시 하려면** 아이콘 파일의 경로입니다.  
  
6.  모든 템플릿 변환 구축 및 솔루션을 실행 합니다.  
  
7.  디자이너에서 생성 된 샘플 다이어그램을 엽니다.  
  
     탐색기 3 표시 됩니다  **배우** 노드 아이콘입니다.  
  
> [!NOTE]
>  생성 된 탐색기에 표시 되는 요소에 대 한 노드 아이콘을 설정한 경우 모든 탐색기 노드 아이콘이 표시 됩니다.  아이콘이 설정 된 경우 노드 기본 아이콘이 표시 됩니다.  
  
## 탐색기 노드에 표시 되는 이름을 변경 합니다.  
 모델 요소의 이름이 탐색기에 표시 되는 방법을 변경할 수 있습니다.  다음은 메모 주석 노드를 참조 하는 작업의 이름을 표시 하는 방법을 보여 줍니다.  
  
#### 속성을 표시 하려면  
  
1.  이전 절차에서 만든 솔루션을 엽니다.  
  
2.  주석 속성 이름으로 역할의 복합성을 설정 하 여 단일 도메인 클래스 참조 하는지 확인  **주제** 0에서 1까지 합니다.  속성 이름이 되어서는 안됩니다  **제목**, 관계 이름 이어야 하 고  **CommentReferencesSubject**.  
  
3.  에  **DSL 탐색기**, 마우스 오른쪽 단추로  **탐색기 문제** 하 고 다음을 클릭  **새 탐색기 노드 설정 추가**.  
  
     **ExplorerNodeSettings** 노드 아래에 나타납니다에  **사용자 지정 노드 설정** 노드.  
  
4.  선택  **ExplorerNodeSettings**, 다음에  **속성** 창 설정  **클래스** 에  **설명**.  
  
5.  마우스 오른쪽 단추로  **주석** 노드를 클릭 하 고  **새 속성 경로 추가**.  
  
     라는 새 노드가 나타납니다  **표시**.  
  
6.  선택  **속성이 표시**, 다음에  **속성** 창의 값 필드를 클릭  **Path 속성에**.  선택  **설명**, 다음  **CommentReferencesSubject**, 다음  **FlowElement**.  결과 패스 유사 합니다  **CommentReferencesSubject.Subject\/\!제목**.  
  
7.  값 필드의  **속성이**,  **이름**.  
  
8.  모든 템플릿 변환 구축 및 솔루션을 실행 합니다.  
  
9. 디자이너에서 생성 된 샘플 다이어그램을 엽니다.  
  
10. 그리기는  **주석 커넥터** 주석 요소 간의 하는  **Task1** 다이어그램 요소입니다.  
  
     탐색기 노드 주석으로 표시 해야 합니다  **Task1**.  
  
## 노드 숨기기  
 에 경로 추가 하 여 해당 탐색기에서 노드를 숨길 수 있습니다의  **숨겨진 노드가** 의 노드는  **DSL 탐색기**.  다음은 주석 노드를 숨기는 방법을 보여 줍니다.  
  
#### 탐색기 노드를 숨기려면  
  
1.  이전 절차에서 만든 솔루션을 엽니다.  
  
2.  에  **DSL 탐색기**, 마우스 오른쪽 단추로  **탐색기 문제** 하 고 다음을 클릭  **새 도메인 경로 추가**.  
  
     A  **도메인 경로** 에서 나타납니다  **숨겨진 노드가**.  
  
3.  선택  **도메인 경로**, 다음에  **속성** 창의 값 필드를 클릭  **경로 정의**.  선택  **FlowGraph**, 다음  **FlowGraphHasComments**.  결과 패스 유사 합니다  **FlowGraphHasComments.Comments**  
  
4.  모든 템플릿 변환 구축 및 솔루션을 실행 합니다.  
  
5.  디자이너에서 생성 된 샘플 다이어그램을 엽니다.  
  
     탐색기를 표시 합니다는  **배우** 노드를 표시 해야 하는  **메모**  노드.  
  
## 참고 항목  
 [Domain\-Specific Language Tools Glossary](http://msdn.microsoft.com/ko-kr/ca5e84cb-a315-465c-be24-76aa3df276aa)