---
title: "요소 만들기 및 이동 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.dsltools.dsldesigner.elementmergedirective"
helpviewer_keywords: 
  - "도메인별 언어에서 요소 병합 지시문"
ms.assetid: cbd28f15-dfd7-46bd-ab79-5430e3ed83c8
caps.latest.revision: 36
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 36
---
# 요소 만들기 및 이동 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

요소를 끌어다 놓을 수, 붙여넣기 또는 도구 상자에서 또는 이동 작업을 허용할 수 있습니다. 지정 된 관계를 사용 하 여 대상 요소에 연결 하는 이동된 요소가 있을 수 있습니다.  
  
 요소 병합 지시문 EMD ()를 지정 하나의 모델 요소가 *병합* 다른 모델 요소에 있습니다. 이런 경우:  
  
-   다이어그램 또는 셰이프를 도구 상자에서 사용자가 끌 합니다.  
  
-   사용자는 탐색기 또는 구획 모양에는 추가 메뉴를 사용 하 여 요소를 만듭니다.  
  
-   사용자 항목 스윔 레인 간에 이동합니다.  
  
-   사용자는 요소를 붙여 넣습니다.  
  
-   프로그램 코드 요소 병합 지시문을 호출합니다.  
  
 생성 작업 복사 작업을 다르게 보이지만 실제로 같은 방식으로 작동 합니다. 요소가 추가 되 면 예를 들어 도구 상자에서 그의 프로토타입을 복제 됩니다. 프로토타입 모델의 다른 부분에서 복사 된 요소와 같은 방식으로 모델에 병합 됩니다.  
  
 EMD의 책임 모델의 특정 위치에 개체 또는 개체 그룹을 해야 병합 하는 방법을 결정 하는 것입니다. 특히, 모델에 병합 된 그룹을 연결 하려면 관계를 인스턴스화해야 결정 합니다. 속성을 설정 하 고 다른 개체를 만들을 지정할 수 있습니다.  
  
 ![DSL & #45입니다. EMD &#95; 병합](../modeling/media/dsl-emd_merge.png "DSL-EMD_Merge")  
요소 병합 지시문의 역할  
  
 EMD는 포함 관계를 정의할 때 자동으로 생성 됩니다. 사용자가 부모에 새 자식 인스턴스를 추가할 때이 기본 EMD 관계의 인스턴스를 만듭니다. 사용자 지정 코드를 추가 하 여 예를 들어 이러한 기본 EMDs를 수정할 수 있습니다.  
  
 또한 사용자가 끌거나 병합 되 고 수신 하는 클래스의 다양 한 조합을 붙여 넣을 수 있도록 DSL 정의에서 사용자 고유의 EMDs를 추가할 수 있습니다.  
  
## <a name="defining-an-element-merge-directive"></a>요소 병합 지시문을 정의합니다.  
 도메인 클래스, 도메인 관계, 모양, 연결선, 및 다이어그램에 요소 병합 지시문을 추가할 수 있습니다. 추가 하거나 수신 하는 도메인 클래스 아래 DSL 탐색기에서 찾을 수 있습니다. 받는 클래스는 이미 모델에와 새 또는 복사 된 요소의 병합할 수에 있는 요소의 도메인 클래스입니다.  
  
 ![DSL & #45입니다. EMD &#95; 세부 정보](../modeling/media/dsl-emd_details.png "DSL-EMD_Details")  
  
  **인덱싱 클래스** 받는 클래스의 멤버에 병합 하는 요소의 도메인 클래스입니다. 설정 하지 않은 경우 인덱싱 클래스의 서브 클래스의 인스턴스에서이 EMD 하 여 병합 될 수도 **서브 클래스에 적용 됩니다.** false입니다.  
  
 병합 지시문의 두 종류가 있습니다.  
  
-   A **프로세스 병합** 지시문 기준이 트리에 새 요소를 연결 하는 관계를 지정 합니다.  
  
-   A **앞으로 병합** 지시문을 다른 수신 요소는 부모 일반적으로 새 요소를 리디렉션합니다.  
  
 지시문을 병합 하는 사용자 지정 코드를 추가할 수 있습니다.  
  
-   설정 **사용 하 여 사용자 지정 허용** 인덱싱 요소의 특정 인스턴스에 대상 요소에 병합 해야 하는지 여부를 결정 하는 코드를 추가 합니다. 도구 상자에서 사용자가 끌, "잘못 된" 포인터 코드 병합 허용 하지 않는 경우에 표시 됩니다.  
  
     예를 들어 받는 요소는 특정 상태에 있을 때만 병합을 허용할 수 있습니다.  
  
-   설정 **사용 하 여 사용자 지정 병합** 추가 하는 변경 내용을 병합을 수행할 때 모델에 대 한 정의를 직접 코드를 제공 합니다.  
  
     예를 들어 모델에 새 위치에서 데이터를 사용 하 여 병합 된 요소에 속성을 설정 수 있습니다.  
  
> [!NOTE]
>  사용자 지정 병합 코드를 작성 하는 경우이 EMD를 사용 하 여 수행 하는 유일한 병합을 영향을 줍니다. 같은 형식의 개체를 병합 하는 다른 EMDs 않거나 EMD는 사용 하지 않고 이러한 개체를 생성 하는 다른 사용자 지정 코드가 있는 경우 다음은 됩니다의 영향을 받지 병합 사용자 지정 코드입니다.  
>   
>  사용자 지정 코드에서 새 요소 또는 새 관계를 항상 처리할 수 있는지 확인 하려는 경우 고려해는 `AddRule` 포함 관계에 대해 및 `DeleteRule` 요소의 도메인 클래스에 있습니다. 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
## <a name="example-defining-an-emd-without-custom-code"></a>예: 사용자 지정 코드 없이 EMD를 정의합니다.  
 다음 예에는 사용자가 기존 도형 도구 상자에서 끌어 동시에 요소와 커넥터를 만들 수 있습니다. 이 예제는 DSL 정의에 EMD를 추가합니다. 이 수정 하기 전에 사용자가 기존 셰이프에 있지만 다이어그램으로 도구를 끌 수 있습니다.  
  
 사용자가 다른 요소는 요소를 붙여 넣을 수도 있습니다.  
  
#### <a name="to-let-users-create-an-element-and-a-connector-at-the-same-time"></a>사용자가 동시에 요소와 커넥터를 만들 수 있도록  
  
1.  사용 하 여 새 DSL을 만들 수는 **최소 언어** 솔루션 템플릿이 있습니다.  
  
     이 DSL을 실행 하면 모양 및 연결선 셰이프 사이 만들 수 있습니다. 새 끌면 **ExampleElement** 기존 도형 도구 상자에서 셰이프입니다.  
  
2.  사용자가 요소를 병합할 수 있도록 `ExampleElement` 셰이프를 만들기에서 새 EMD는 `ExampleElement` 도메인 클래스:  
  
    1.   **DSL 탐색기**, 를 확장 하 고 **도메인 클래스**합니다. 마우스 오른쪽 단추로 클릭 `ExampleElement` 클릭 하 고 **새 요소 병합 지시문 추가**합니다.  
  
    2.  다음 사항을 확인은 **DSL 정보** 창이 열렸는지 새 EMD의 세부 정보를 볼 수 있도록 합니다. (메뉴: **보기**, **다른 창을**, **DSL 정보**.)  
  
3.  설정의 **클래스 인덱싱** 에 어떤 클래스의 요소를 병합할 수를 정의 하는 DSL 세부 정보 창에서 `ExampleElement` 개체입니다.  
  
     이 예에서는 선택 `ExampleElements`, 사용자 기존 요소에 새 요소를 끌 수 있도록 합니다.  
  
     인덱싱 클래스 DSL 탐색기에서 EMD의 이름이 되 고 있는지 확인 합니다.  
  
4.  아래에서 **연결을 만들어 프로세스 병합**, 두 개의 경로 추가 합니다.  
  
    1.  하나의 경로 부모 모델에 새 요소를 연결합니다. 입력 해야 하는 경로 식에서에서 이동는 기존 요소를 포함 관계를 통해 부모 모델 합니다. 마지막으로, 새 요소가 할당 될 새 링크에는 역할을 지정 합니다. 경로 다음과 같습니다.  
  
         `ExampleModelHasElements.ExampleModel/!ExampleModel/.Elements`  
  
    2.  다른 경로에 기존 요소는 새 요소를 연결합니다. 경로 식은 참조 관계 및 새 요소가 할당 하는 역할을 지정 합니다. 이 경로 다음과 같습니다.  
  
         `ExampleElementReferencesTargets.Sources`  
  
     각 경로 작성 하는 경로 탐색 도구를 사용할 수 있습니다.  
  
    1.  아래에서 **프로세스 병합 경로에서 링크를 만들어**, 클릭 **\< 경로 추가>**합니다.  
  
    2.  목록 항목의 오른쪽에 있는 드롭다운 화살표를 클릭 합니다. 트리 뷰가 나타납니다.  
  
    3.  지정 하려면 경로 구성 하는 트리에서 노드를 확장 합니다.  
  
5.  DSL을 테스트 합니다.  
  
    1.  F5 키를 눌러 다시 빌드하고 솔루션을 실행 합니다.  
  
         다시 작성 새 DSL 정의에 맞게 텍스트 템플릿에서 생성된 된 코드를 업데이트할 수는 평소 보다 오래 걸릴 됩니다.  
  
    2.  때의 실험적 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 는 DSL의 모델 파일을 열고 시작 합니다. 일부 예제에서는 요소를 만듭니다.  
  
    3.  끌어는 **예제 요소** 기존 도형에는 도구입니다.  
  
         새 도형을 나타나고 한 커넥터와 함께 기존 셰이프에 연결 됩니다.  
  
    4.  기존 모양을 복사 합니다. 다른 셰이프를 선택 하 고 붙여 넣습니다.  
  
         첫 번째 모양의 복사본이 생성 됩니다.  새 이름이 하 고 두 번째 셰이프 연결선에 연결 됩니다.  
  
 이 프로시저에서 다음 사항을 확인 합니다.  
  
-   요소 병합 지시문을 만들어 적용할 다른 모든 요소의 모든 클래스를 허용할 수 있습니다. 받는 도메인 클래스에는 EMD 만들어지고 허용된 도메인 클래스에 지정 된 **Index 클래스** 필드입니다.  
  
-   경로 정의 하 여 지정할 수 있습니다 링크 해야 기존 모델에 새 요소를 연결 하는 데 사용 됩니다.  
  
     지정 된 링크는 포함 관계 하나 포함 되어야 합니다.  
  
-   EMD는 모두 만들기를를 선택 하 고도 붙여넣기 작업에 영향을 줍니다.  
  
     EMD는를 사용 하 여 명시적으로 호출 수를 새 요소를 만드는 사용자 지정 코드를 작성 하는 경우는 `ElementOperations.Merge` 메서드. 이렇게 하면 코드에서 링크로 연결 되 새 요소를 모델에 동일한 방식으로 다른 작업. 자세한 내용은 참조 [복사 동작 사용자 지정](../modeling/customizing-copy-behavior.md)합니다.  
  
## <a name="example-adding-custom-accept-code-to-an-emd"></a>예: EMD Custom Accept 코드 추가  
 사용자 지정 코드에 EMD를 추가 하면 좀 더 복잡 한 병합 동작을 정의할 수 있습니다. 이 간단한 예제에서 다이어그램으로 고정 된 수의 요소를 보다 많은 추가 사용자 수 없습니다. 예제에서는 EMD는 포함 관계를 함께 제공 되는 기본값을 수정 합니다.  
  
#### <a name="to-write-custom-accept-code-to-restrict-what-the-user-can-add"></a>사용자에 추가할 수를 제한 하려면 Custom Accept 코드를 작성 하려면  
  
1.  사용 하 여 DSL을 만들 수는 **최소 언어** 솔루션 템플릿이 있습니다. DSL 정의 다이어그램을 엽니다.  
  
2.  DSL 탐색기에서 **도메인 클래스**, `ExampleModel`, **요소 병합 지시문**합니다. 라는 요소 병합 지시문 선택 `ExampleElement`합니다.  
  
     이 EMD 제어 사용자 새로 만들 수 방법을 `ExampleElement` 예를 들어 끌어서 도구 상자에서 모델의 개체입니다.  
  
3.  에 **DSL 정보** 창에서 **사용 하 여 사용자 지정 허용**합니다.  
  
4.  솔루션을 다시 빌드합니다. 모델에서 생성된 된 코드를 업데이트할 수는 평소 보다 오래 이동 됩니다.  
  
     빌드 오류가 보고 된와 유사 하 게 됩니다: "Company.ElementMergeSample.ExampleElement 않습니다 하지에 대 한 정의가 CanMergeExampleElement..."  
  
     메서드를 구현 해야 `CanMergeExampleElement`합니다.  
  
5.  새 코드 파일에 **Dsl** 프로젝트입니다. 해당 콘텐츠를 다음 코드로 바꿉니다 하 고 프로젝트의 네임 스페이스에 네임 스페이스를 변경 합니다.  
  
    ```c#  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace Company.ElementMergeSample // EDIT.  
    {  
      partial class ExampleModel  
      {  
        /// <summary>  
        /// Called whenever an ExampleElement is to be merged into this ExampleModel.  
        /// This happens when the user pastes an ExampleElement  
        /// or drags from the toolbox.  
        /// Determines whether the merge is allowed.  
        /// </summary>  
        /// <param name="rootElement">The root element in the merging EGP.</param>  
        /// <param name="elementGroupPrototype">The EGP that the user wants to merge.</param>  
        /// <returns>True if the merge is allowed</returns>  
        private bool CanMergeExampleElement(ProtoElementBase rootElement, ElementGroupPrototype elementGroupPrototype)  
        {  
          // Allow no more than 4 elements to be added:  
          return this.Elements.Count < 4;  
        }  
      }  
    }  
  
    ```  
  
     이 간단한 예제에서는 부모 모델에 병합할 수 있는 요소의 수를 제한 합니다. 더 흥미로운 조건에 대 한 속성 및 링크를 받는 개체의 메서드를 검사할 수 있습니다. 제공 되는 병합 요소의 속성을 검사할 수도 있습니다는 <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>합니다. 에 대 한 자세한 내용은 `ElementGroupPrototypes`, 참조 [복사 동작 사용자 지정](../modeling/customizing-copy-behavior.md)합니다. 모델을 읽는 코드를 작성 하는 방법에 대 한 자세한 내용은 참조 [탐색 및 업데이트 프로그램 코드에서 모델](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.  
  
6.  DSL을 테스트 합니다.  
  
    1.  F5 키를 눌러 솔루션을 다시 빌드해야 합니다. 때의 실험적 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 가 열리고, DSL의 인스턴스를 엽니다.  
  
    2.  여러 가지 방법으로 새 요소를 만듭니다.  
  
        1.  끌어는 **예제 요소** 도구에서 다이어그램입니다.  
  
        2.  에 **예제 모델 탐색기**, 루트 노드를 마우스 오른쪽 단추로 클릭 하 고 클릭 한 다음 **새 예제에서는 요소 추가**합니다.  
  
        3.  복사 하는 요소 다이어그램에 붙여넣습니다.  
  
    3.  요소를 추가 하려면 4 개 이상의 모델에 이러한 방법으로 사용할 수 없음을 확인 합니다. 요소 병합 지시문을 사용 하 여 모두 때문입니다.  
  
## <a name="example-adding-custom-merge-code-to-an-emd"></a>예: EMD 병합 하는 사용자 지정 코드 추가  
 사용자 지정 병합 코드에서 사용자는 도구를 끌어 요소에 붙여넣을 때 수행할 작업을 정의할 수 있습니다. 두 가지 방법으로 사용자 지정 병합을 정의할 수 있습니다.  
  
1.  설정 **사용 하 여 사용자 지정 병합** 하 고 필요한 코드를 제공 합니다. 코드는 생성 된 병합 코드를 대체 합니다. 완전히 병합이 수행 되는 작업을 재정의 하려는 경우이 옵션을 사용 합니다.  
  
2.  재정의 `MergeRelate` 메서드를 선택적으로 `MergeDisconnect` 메서드. 이 위해 설정 해야는 **Generates Double Derived** 도메인 클래스의 속성입니다. 코드는 기본 클래스에서 생성 된 병합 코드를 호출할 수 있습니다. 병합이 수행 된 후 추가 작업을 수행 하려는 경우이 옵션을 사용 합니다.  
  
 이러한 접근 방법은이 EMD를 사용 하 여 수행 하는 병합을만 영향을 줍니다. 정의 하는 대체 항목은 병합 된 요소를 만들 수 있는 방법을 모두에 적용 하려는 경우는 `AddRule` 포함 관계에 대해 및 `DeleteRule` 병합 된 도메인 클래스에 있습니다. 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
#### <a name="to-override-mergerelate"></a>MergeRelate 재정의 하려면  
  
1.  DSL 정의에서 코드를 추가 하려면 원하는 EMD를 정의 해야 합니다. 경로 추가 하 고 정의할 수를 이전 섹션에 설명 된 대로 사용자 지정 코드를 허용 합니다.  
  
2.  DslDefinition 다이어그램에서 병합의 받는 클래스를 선택 합니다. 일반적으로 포함 관계의 원본 끝에 클래스입니다.  
  
     예를 들어 최소 언어 솔루션에서 생성 된 DSL에서 선택 `ExampleModel`합니다.  
  
3.  에 **속성** 창의 설정 **Generates Double Derived** 를 **true**합니다.  
  
4.  솔루션을 다시 빌드합니다.  
  
5.  콘텐츠를 검사할 **Dsl\Generated Files\DomainClasses.cs**합니다. 명명 된 메서드에 대 한 검색 `MergeRelate` 해당 콘텐츠를 검사 합니다. 사용자가 자체 버전을 작성 하는 데 도움이 됩니다.  
  
6.  새 코드 파일을 받는 클래스에 대 한 partial 클래스를 작성 한 재정의 `MergeRelate` 메서드. 기본 메서드를 호출 해야 합니다. 예:  
  
    ```c#  
    partial class ExampleModel  
    {  
      /// <summary>  
      /// Called when the user drags or pastes an ExampleElement onto the diagram.  
      /// Sets the time of day as the name.  
      /// </summary>  
      /// <param name="sourceElement">Element to be added</param>  
      /// <param name="elementGroup">Elements to be merged</param>  
      protected override void MergeRelate(ModelElement sourceElement, ElementGroup elementGroup)  
      {  
        // Connect the element according to the EMD:  
        base.MergeRelate(sourceElement, elementGroup);  
  
        // Custom actions:   
        ExampleElement mergingElement = sourceElement as ExampleElement;  
        if (mergingElement != null)  
        {  
          mergingElement.Name = DateTime.Now.ToLongTimeString();  
        }  
      }  
    }  
  
    ```  
  
#### <a name="to-write-custom-merge-code"></a>병합 하는 사용자 지정 코드를 작성 하려면  
  
1.   **Dsl\Generated Code\DomainClasses.cs**, 명명 된 메서드에 검사 `MergeRelate`합니다. 이러한 메서드는 새 요소와 기존 모델 간의 링크를 만듭니다.  
  
     또한 라는 이름의 메서드를 검사 `MergeDisconnect`합니다. 이러한 메서드 삭제 될 때 모델에서 요소를 연결 해제 합니다.  
  
2.   **DSL 탐색기**, 을 선택 하거나 사용자 지정 하 고 원하는 요소 병합 지시문을 만듭니다. 에 **DSL 정보** 창의 설정 **사용 하 여 사용자 지정 병합**합니다.  
  
     이 옵션을 설정 하는 경우는 **프로세스 병합** 및 **앞으로 병합** 옵션은 무시 됩니다. 코드 대신 사용 됩니다.  
  
3.  솔루션을 다시 빌드합니다. 모델에서 생성된 된 코드 파일을 업데이트할 수는 평소 보다 시간이 오래 걸립니다.  
  
     오류 메시지가 표시 됩니다. 생성된 된 코드에 대 한 지침을 보려면 오류 메시지를 두 번 클릭 합니다. 이러한 지침은 두 가지 메서드를 입력 하 라는 메시지가 `MergeRelate`*YourDomainClass* 및 `MergeDisconnect`*YourDomainClass*  
  
4.  별도 코드 파일의 partial 클래스 정의에 메서드를 작성 합니다. 앞에서 검사 하는 예제 필요한 권장 해야 합니다.  
  
 사용자 지정 병합 코드를 직접 개체 및 관계를 만드는 코드는 영향을 주지 않습니다 하 고 다른 EMDs 영향을 주지 않습니다. 요소를 만든 방법에 관계 없이 추가 변경 내용을 구현 된다는 하는 것이 좋습니다 쓰기는 `AddRule` 및 `DeleteRule` 대신 합니다. 자세한 내용은 참조 [규칙 전파 변경 내에서 모델](../modeling/rules-propagate-changes-within-the-model.md)합니다.  
  
## <a name="redirecting-a-merge-operation"></a>병합 작업을 리디렉션  
 앞으로 병합 지시문에는 병합 작업의 대상을 리디렉션합니다. 일반적으로 새 대상이 초기 대상의 포함 부모입니다.  
  
 예를 들어 구성 요소 다이어그램 서식 파일을 사용 하 여 만든 DSL, 포트 구성 요소에 포함 되어 있습니다. 포트 구성 요소 셰이프의 가장자리에 있는 작은 모양으로 표시 됩니다. 사용자는 포트 도구 구성 요소 셰이프를 끌어 포트를 만듭니다. 하지만 때로는 실수로 끌어서 포트 도구는 구성 요소는 대신 기존 포트를 하 고 작업이 실패 합니다. 이 기존 포트를 여러 가지 경우는 간단한 실수. 이 불법이를 방지 하려면 사용자를 위해 기존 포트를 끌어 놓을 수 있지만 부모 구성 요소에 리디렉션 동작 포트를 허용할 수 있습니다. 작업 대상 요소는 구성 요소 처럼 작동 합니다.  
  
 구성 요소 모델 솔루션에는 앞으로 병합 지시문을 만들 수 있습니다. 컴파일하고 원래 솔루션을 실행 하는 경우 사용자가 원하는 수의를 끌 수 표시 됩니다 **입력 포트가** 또는 **출력 포트** 에서 요소는 **도구 상자** 에 **구성 요소** 요소입니다. 그러나 기존 포트를 포트를 끌 수 없습니다. 사용할 수 없는 포인터이 이동이 활성화 되지 않은 것을 경고 합니다. 하지만 하는 포트를 실수로 정방향 병합 지시문을 만들 수는 기존 삭제 **입력 포트** 로 전달 되는 **구성 요소** 요소입니다.  
  
#### <a name="to-create-a-forward-merge-directive"></a>앞으로 병합 지시문을 만들려면  
  
1.  만들기는 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 구성 요소 모델 템플릿을 사용 하 여 솔루션입니다.  
  
2.  표시는 **DSL 탐색기** DslDefinition.dsl을 열어서 합니다.  
  
3.  에 **DSL 탐색기**, 를 확장 하 고 **도메인 클래스**합니다.  
  
4.   **ComponentPort** 추상 도메인 클래스는 둘 다의 기본 클래스 **InPort** 및 **OutPort**합니다. 마우스 오른쪽 단추로 클릭 **ComponentPort** 클릭 하 고 **새 요소 병합 지시문 추가**합니다.  
  
     새 **요소 병합 지시문** 노드가 아래에 표시 된 **요소 병합 지시문** 노드.  
  
5.  선택 된 **요소 병합 지시문** 노드와 열기는 **DSL 세부 정보** 창.  
  
6.  인덱싱 클래스 목록에서 선택 **ComponentPort**합니다.  
  
7.  선택 **다른 도메인 클래스에는 병합 전달**합니다.  
  
8.  경로 선택 목록에서 확장 **ComponentPort**, 를 확장 하 고 **ComponentHasPorts**, 를 선택한 다음 **구성 요소**합니다.  
  
     새 경로는이 이와 유사 합니다.  
  
     **ComponentHasPorts.Component/!Component**  
  
9. 솔루션을 저장 하 고 다음 템플릿이에서 맨 오른쪽 단추를 클릭 하 여 변환 된 **솔루션 탐색기** 도구 모음입니다.  
  
10. 솔루션을 빌드하고 실행합니다. 새 인스턴스 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 나타납니다.  
  
11.  **솔루션 탐색기**, Sample.mydsl를 엽니다. 다이어그램 및 **ComponentLanguage 도구 상자** 나타납니다.  
  
12. 끌기는 **입력 포트** 에서 **도구 상자** 다른 **입력 포트가 있습니다.** 다음으로 끌어는 **OutputPort** 에 **InputPort** 다음에 다른 **OutputPort**.  
  
     사용할 수 없는 포인터 표시 되지 않아야 하 고 새 수 있어야 **입력 포트가** 기존에 있습니다. 새 **입력 포트가** 다른 지점으로 끌어는 **구성 요소**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도구 및 도구 상자 사용자 지정](../modeling/customizing-tools-and-the-toolbox.md)   
 [회로 다이어그램 샘플 DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)