---
title: Windows Forms 기반 도메인별 언어 만들기
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 8f4cfe9549880646fe9ba0a487045b005366c075
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749478"
---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Windows Forms 기반 도메인별 언어 만들기
Windows Forms를 사용 하 여 DSL 다이어그램을 사용 하는 대신 도메인 특정 언어 (DSL) 모델의 상태를 표시 합니다. 이 항목에서는 Windows Form DSL에 바인딩, 사용 하 여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK입니다.

 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png) A DSL 인스턴스를 모델 탐색기 및 Windows 폼 UI를 표시 합니다.

## <a name="creating-a-windows-forms-dsl"></a>Windows Forms DSL 만들기
 **최소 WinForm 디자이너** DSL 서식 파일은 고유한 요구 사항에 맞게 수정할 수 있는 최소 DSL를 만듭니다.

#### <a name="to-create-a-minimal-winforms-dsl"></a>최소 WinForms DSL를 만들려면

1.  DSL 만들기는 **최소 WinForm 디자이너** 템플릿.

     이 연습에서는 다음 이름이 간주 됩니다.

    |||
    |-|-|
    |솔루션, DSL 이름|FarmApp|
    |네임스페이스|Company.FarmApp|

2.  서식 파일을 제공 하는 초기 예제를 시험해:

    1.  모든 템플릿 변환 합니다.

    2.  빌드 및 샘플을 실행 (**CTRL + f 5**).

    3.  Visual Studio의 실험적 인스턴스를 열고는 `Sample` 디버깅 프로젝트 파일에에서 있습니다.

         Windows Forms 컨트롤에 표시 되는지 확인 합니다.

         탐색기에 표시 되는 모델의 요소를 볼 수 있습니다.

         일부 요소는 폼 또는 탐색기에서 솔루션에 추가 하 고 다른 디스플레이에 표시 되는지 확인 합니다.

 기본 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], DSL 솔루션에 대 한 다음 사항을 확인 합니다.

-   `DslDefinition.dsl` 다이어그램 요소를 포함합니다. 즉,이 DSL의 인스턴스 모델을 볼 DSL 다이어그램을 사용 하지 것입니다. 대신 Windows Form 모델 바인딩될 하 고 폼에서 요소가 모델에 표시 됩니다.

-   이외에 `Dsl` 및 `DslPackage` 프로젝트, 솔루션 라는 세 번째 프로젝트가 포함 되어 `UI.` **UI** 프로젝트는 Windows Forms 컨트롤의 정의 포함 합니다. `DslPackage` 에 따라 달라 집니다 `UI`, 및 `UI` 에 따라 달라 집니다 `Dsl`합니다.

-   에 `DslPackage` 프로젝트를 `UI\DocView.cs` 에 정의 되어 있는 Windows Forms 컨트롤을 표시 하는 코드가 포함 된 `UI` 프로젝트.

-   `UI` DSL에 바인딩된 양식 컨트롤의 작업 예제 프로젝트에 포함 되어 있습니다. 그러나 DSL 정의 변경 된 경우 작동 하지 않습니다. `UI` 프로젝트에 포함 되어 있습니다.

    -   라는 Windows Forms 클래스 `ModelViewControl`합니다.

    -   라는 파일 `DataBinding.cs` 의 다른 부분 정의 포함 된 `ModelViewControl`합니다. 해당 콘텐츠를 보려면 **솔루션 탐색기**선택을 파일에 대 한 바로 가기 메뉴를 열고 **코드 보기**합니다.

### <a name="about-the-ui-project"></a>UI 프로젝트에 대 한
 고유한 DSL 정의 하는 DSL 정의 파일을 업데이트 하는 경우에 컨트롤을 업데이트 해야 합니다는 `UI` DSL 표시 하는 프로젝트입니다. 와 달리는 `Dsl` 및 `DslPackage` 프로젝트, 샘플 `UI` 프로젝트에서 생성 되지 않습니다 `DslDefinitionl.dsl`합니다. 이 연습에서 설명 되지 않는 하지만 원하는 경우 코드를 생성 하는.tt 파일을 추가할 수 있습니다.

## <a name="updating-the-dsl-definition"></a>DSL 정의 업데이트
 DSL 정의이 연습에서 사용 되는 다음과 같은 있습니다.

 ![DSL&#45;Wpf&#45;1](../modeling/media/dsl-wpf-1.png)

#### <a name="to-update-the-dsl-definition"></a>DSL 정의 업데이트 하려면

1.  DSL 디자이너에서 DslDefinition.dsl를 엽니다.

2.  삭제 **ExampleElement**

3.  이름 바꾸기는 **ExampleModel** 도메인 클래스를 `Farm`합니다.

     명명 된 추가 도메인 속성 지정 `Size` 형식의 **Int32**, 및 `IsOrganic` 형식의 **부울**합니다.

    > [!NOTE]
    >  루트 도메인 클래스를 삭제 하 고 그런 다음 새 루트를 만들 경우 편집기 루트 클래스 속성을 다시 설정 해야 합니다. **DSL 탐색기**선택, **편집기**합니다. 그런 다음 속성 창에서 설정 **루트 클래스** 를 `Farm`합니다.

4.  사용 하 여는 **도메인 클래스 라는** 다음 도메인 클래스를 만드는 도구:

    -   `Field` -이 추가 도메인 속성 지정 라는 `Size`합니다.

    -   `Animal` -속성 창에서 설정 **상속 한정자** 를 **추상**합니다.

5.  사용 하 여는 **도메인 클래스** 도구는 다음 클래스를 사용 합니다.

    -   `Sheep`

    -   `Goat`

6.  사용 하 여는 **상속** 도구를 `Goat` 및 `Sheep` 에서 상속 `Animal`합니다.

7.  사용 하 여는 **포함** 포함 하는 도구 `Field` 및 `Animal` 아래 `Farm`합니다.

8.  다이어그램을 정리 하는 데 좋습니다. 사용 하 여 중복 된 요소 수를 줄이려면는 **여기에 하위 트리 Bring** 리프 요소의 바로 가기 메뉴에서 명령을 합니다.

9. **모든 템플릿 변환** 솔루션 탐색기의 도구 모음에서입니다.

10. 빌드는 **Dsl** 프로젝트.

    > [!NOTE]
    >  이 단계에서 다른 프로젝트 오류 없이 빌드되지 않습니다. 그러나 해당 어셈블리를 데이터 원본 마법사를 사용할 수 있도록 Dsl 프로젝트를 빌드할 하려고 합니다.

## <a name="updating-the-ui-project"></a>UI 프로젝트 업데이트
 이제 DSL 모델에 저장 된 정보를 표시 하는 새 사용자 정의 컨트롤을 만들 수 있습니다. 모델에 사용자 정의 컨트롤을 연결 하는 가장 쉬운 방법은 데이터 바인딩을 통해 됩니다. 데이터 바인딩 이라는 어댑터 유형을 **ModelingBindingSource** Dsl VMSDK 아닌 인터페이스에 연결 하도록 설계 된.

#### <a name="to-define-your-dsl-model-as-a-data-source"></a>DSL 모델을 데이터 원본으로 정의 하려면

1.  에 **데이터** 메뉴 선택 **데이터 소스 표시**합니다.

     **데이터 소스** 창이 열립니다.

     선택 **새 데이터 소스 추가**합니다. **데이터 소스 구성 마법사** 열립니다.

2.  선택 **개체**, **다음**합니다.

     확장 **Dsl**, **Company.FarmApp**를 선택 하 고 **팜**,이 모델의 루트 클래스입니다. **마침**을 선택합니다.

     솔루션 탐색기에서는 **UI** 프로젝트에 포함 되어 이제 **Properties\DataSources\Farm.datasource**

     속성 및 관계 모델 클래스의 데이터 소스 창에 나타납니다.

     ![DslWpf&#45;3](../modeling/media/dslwpf-3.png)

#### <a name="to-connect-your-model-to-a-form"></a>폼에 모델에 연결 하려면

1.  에 **UI** 프로젝트를 기존.cs 파일을 모두 삭제 합니다.

2.  새로 추가 **사용자 정의 컨트롤** 라는 파일 `FarmControl` 에 **UI** 프로젝트.

3.  에 **데이터 원본** 드롭 다운 메뉴에서 창을 **팜**, 선택 **세부 정보**합니다.

     다른 속성에 대 한 기본 설정을 그대로 둡니다.

4.  디자인 뷰에서 FarmControl.cs를 엽니다.

     끌기 **팜** FarmControl 데이터 소스 창에서.

     컨트롤의 집합이 나타나고, 각 속성에 대 한 관계 속성 컨트롤을 생성 하지 않습니다.

5.  삭제 **farmBindingNavigator**합니다. 이 자동으로 생성 된 `FarmControl` 디자이너 하지만이 응용 프로그램에 유용 하지 않습니다.

6.  도구 상자를 사용 하 여의 두 인스턴스를 만들 **DataGridView**, 이름을 지정 하 고 `AnimalGridView` 및 `FieldGridView`합니다.

    > [!NOTE]
    >  컨트롤에 데이터 소스 창에서 필드 및 동물 항목을 끌어 하는 대체 단계가입니다. 이 작업에는 자동으로 데이터 표 및 그리드 보기와 데이터 원본 간의 바인딩을 만듭니다. 그러나이 바인딩 Dsl에 대 한 올바르게 작동 하지 않습니다. 따라서 하는 것이 데이터 표 및 바인딩을 만들 수동으로 합니다.

7.  도구 상자에 포함 되어 있지 않으면는 **ModelingBindingSource** 도구를 추가 합니다. 바로 가기 메뉴는 **데이터** 탭에서 선택 **항목 선택**합니다. 에 **도구 상자 항목 선택** 대화 상자에서 **ModelingBindingSource** 에서 **.NET Framework 탭**합니다.

8.  도구 상자를 사용 하 여의 두 인스턴스를 만들 **ModelingBindingSource**, 이름을 지정 하 고 `AnimalBinding` 및 `FieldBinding`합니다.

9. 설정의 **DataSource** 각 속성 **ModelingBindingSource** 를 **farmBindingSource**합니다.

     설정의 **DataMember** 속성을 **동물** 또는 **필드**합니다.

10. 설정의 **DataSource** 의 속성 `AnimalGridView` 를 `AnimalBinding`, 및의 `FieldGridView` 를 `FieldBinding`합니다.

11. 프로그램 경험해 팜 컨트롤의 레이아웃을 조정 합니다.

 **ModelingBindingSource** Dsl 관련 된 몇 가지 기능을 수행 하는 어댑터:

-   VMSDK 저장소 트랜잭션을에 업데이트를 래핑합니다.

     예를 들어 그리드 보기에서에서 한 행을 삭제 하는 경우 일반 바인딩 트랜잭션 예외가 발생 합니다.

-   사용자가 행을 선택 하면 속성 창 데이터 표 행 대신 해당 모델 요소와의 속성을 표시, 되도록 조정 합니다.

 ![DslWpf4](../modeling/media/dslwpf4.png) 스키마 데이터 원본 및 뷰 사이 링크 합니다.

#### <a name="to-complete-the-bindings-to-the-dsl"></a>DSL에 대 한 바인딩을 완료 하려면

1.  다음 코드를 별도 코드 파일에 추가 된 **UI** 프로젝트:

    ```csharp
    using System.ComponentModel;
    using Microsoft.VisualStudio.Modeling;
    using Microsoft.VisualStudio.Modeling.Design;

    namespace Company.FarmApp
    {
      partial class FarmControl
      {
        public IContainer Components { get { return components; } }

        /// <summary>Binds the WinForms data source to the DSL model.
        /// </summary>
        /// <param name="nodelRoot">The root element of the model.</param>
        public void DataBind(ModelElement modelRoot)
        {
          WinFormsDataBindingHelper.PreInitializeDataSources(this);
          this.farmBindingSource.DataSource = modelRoot;
          WinFormsDataBindingHelper.InitializeDataSources(this);
        }
      }
    }
    ```

2.  에 **DslPackage** 프로젝트, 편집 **DslPackage\DocView.tt** 다음 변수 정의 업데이트 하려면:

    ```csharp
    string viewControlTypeName = "FarmControl";
    ```

## <a name="testing-the-dsl"></a>DSL 테스트
 이제 DSL 솔루션 빌드하고 나중에 추가할 추가 개선 하려면 수는 있지만 실행할 수 있습니다.

#### <a name="to-test-the-dsl"></a>DSL를 테스트 하려면

1.  솔루션을 빌드하고 실행합니다.

2.  Visual Studio의 실험적 인스턴스를 열고는 **샘플** 파일입니다.

3.  에 **FarmApp 탐색기**에서 바로 가기 메뉴를 열고는 **팜** 루트 노드를 선택 하 고 **새 염소 추가**합니다.

     `Goat1` 에 표시 된 **동물** 보기.

    > [!WARNING]
    >  에 바로 가기 메뉴를 사용 해야 합니다는 **팜** 노드를 하지는 **동물** 노드.

4.  선택 된 **팜** 루트 노드 및 해당 속성을 확인 합니다.

     폼 보기에서 변경 된 **이름** 또는 **크기** 팜의 합니다.

     때 속성 창에서 해당 속성 변경 내용 폼의 각 필드를 다른 곳으로 이동 합니다.

## <a name="enhancing-the-dsl"></a>DSL 향상

#### <a name="to-make-the-properties-update-immediately"></a>즉시 업데이트 속성을 확인 하려면

1.  FarmControl.cs의 디자인 뷰에서 단순 필드 이름, 크기 또는 IsOrganic 등을 선택 합니다.

2.  속성 창에서 확장 **DataBindings** 엽니다 **(고급)** 합니다.

     에 **서식 지정 및 고급 바인딩** 대화에서 **데이터 원본 업데이트 모드**, 선택 **OnPropertyChanged**합니다.

3.  솔루션을 빌드하고 실행합니다.

     팜 모델 변경 내용 즉시의 해당 속성 필드의 내용을 변경 하면 있는지 확인 하십시오.

#### <a name="to-provide-add-buttons"></a>추가 단추를 제공 하려면

1.  FarmControl.cs의 디자인 뷰에서 도구 상자를 사용 하 여 폼에 단추를 만듭니다.

     이름과 단추의 텍스트를 예를 들어 편집 `New Sheep`합니다.

2.  단추 뒤에 있는 코드 (예를 들어 두 번 클릭)에서 엽니다.

     다음과 같이 편집 합니다.

    ```csharp
    private void NewSheepButton_Click(object sender, EventArgs e)
    {
      using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
      {
        elementOperations.MergeElementGroup(farm,
          new ElementGroup(new Sheep(farm.Partition)));
        t.Commit();
      }
    }

    // The following code is shared with other add buttons:
    private ElementOperations operationsCache = null;
    private ElementOperations elementOperations
    {
      get
      {
        if (operationsCache == null)
        {
          operationsCache = new ElementOperations(farm.Store, farm.Partition);
        }
        return operationsCache;
      }
    }
    private Farm farm
    {
      get { return this.farmBindingSource.DataSource as Farm; }
    }

    ```

     또한 다음 지시문을 삽입 해야 합니다.

    ```csharp

    using Microsoft.VisualStudio.Modeling;

    ```

3.  염소 및 필드에 대 한 유사한 단추를 추가 합니다.

4.  솔루션을 빌드하고 실행합니다.

5.  새로 만들기 단추 항목을 추가 확인 합니다. 새 항목 FarmApp 탐색기에서 및 적절 한 데이터 그리드 보기에 표시 됩니다.

     데이터 그리드 보기에 있는 요소의 이름을 편집할 수 있습니다. 여기에서 삭제할 수 있습니다.

 ![DSL&#45;Wpf&#45;2](../modeling/media/dsl-wpf-2.png)

### <a name="about-the-code-to-add-an-element"></a>요소를 추가 하는 코드에 대 한
 새 요소 단추에 대 한 다음과 같은 대체 코드를 좀 더 간단 합니다.

```csharp
private void NewSheepButton_Click(object sender, EventArgs e)
{
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))
  {
    farm.Animals.Add(new Sheep(farm.Partition)); ;
    t.Commit();
  }
}

```

 그러나이 코드는 새 항목에 대 한 기본 이름을 설정 하지 않습니다. 에 정의 된 모든 사용자 지정 된 병합 실행 되지 않습니다는 **요소 병합 지시문** DSL의 정의 된 모든 병합을 사용자 지정 코드는 실행 되지 않습니다.

 사용 하는 권장 따라서 <xref:Microsoft.VisualStudio.Modeling.ElementOperations> 새 요소를 만듭니다. 자세한 내용은 참조 [사용자 지정 요소 만들기 및 이동](../modeling/customizing-element-creation-and-movement.md)합니다.

## <a name="see-also"></a>참고 항목

- [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)
- [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [Visual Studio용 모델링 SDK - 도메인별 언어](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)