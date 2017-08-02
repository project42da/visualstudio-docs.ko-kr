---
title: "Windows Forms 기반 도메인별 언어 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 452318ff-8ecf-46d0-8ca0-4013d0cdafaf
caps.latest.revision: 17
author: alancameronwills
ms.author: awills
manager: douge
translationtype: Machine Translation
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: c9caf1da3e6e9d065a94e6b12b7699cd5a381ea2
ms.lasthandoff: 02/22/2017

---
# <a name="creating-a-windows-forms-based-domain-specific-language"></a>Windows Forms 기반 도메인별 언어 만들기
Windows Forms를 사용 하 여 DSL 다이어그램을 사용 하는 대신 도메인별 언어 (DSL) 모델의 상태를 표시 합니다. 이 항목에서는 DSL에 Windows Form을 바인딩를 사용 하 여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK.  
  
 ![DSL-Wpf-2](~/modeling/media/dsl-wpf-2.png "DSL-Wpf-2")  
Windows 폼 UI를 모델 탐색기에 표시 된 DSL 인스턴스.  
  
## <a name="creating-a-windows-forms-dsl"></a>Windows Forms DSL 만들기  
 **최소 WinForm Designer** DSL 템플릿은 사용자 고유의 요구 사항에 맞게 수정할 수 있는 최소한의 DSL을 만듭니다.  
  
#### <a name="to-create-a-minimal-winforms-dsl"></a>최소 WinForms DSL을 만들려면  
  
1.  DSL을 만들 수는 **최소 WinForm Designer** 템플릿.  
  
     이 연습에서는 다음과 같은 이름이 사용 됩니다.  
  
    |||  
    |-|-|  
    |솔루션, DSL 이름|FarmApp|  
    |네임스페이스|Company.FarmApp|  
  
2.  템플릿에서 제공 하는 초기 예제를 실험:  
  
    1.  모든 템플릿 변환 합니다.  
  
    2.  빌드 및 샘플을 실행 (**CTRL + f&5;**).  
  
    3.  Visual Studio의 실험적 인스턴스를 열고는 `Sample` 디버깅 프로젝트의 파일입니다.  
  
         이 Windows Forms 컨트롤에 표시 되는지 확인 합니다.  
  
         탐색기에 표시 되는 모델의 요소를 볼 수 있습니다.  
  
         폼 또는 탐색기의 일부 요소를 추가 하 고 다른 화면에 나타납니다.  
  
 기본 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], DSL 솔루션에 대 한 다음 사항에 유의 합니다.  
  
-   `DslDefinition.dsl`다이어그램 요소를 포함합니다. 즉,이 DSL의 인스턴스 모델을 볼 DSL 다이어그램을 사용 하지 것입니다. 대신, 모델에는 Windows Form 바인딩합니다 하 고 폼에서 요소가 모델에 표시 됩니다.  
  
-   이외에 `Dsl` 및 `DslPackage` 프로젝트, 솔루션 라는 세 번째 프로젝트에 포함 되어 `UI.` **UI** 프로젝트는 Windows Forms 컨트롤의 정의 포함 합니다. `DslPackage`에 따라 달라 집니다 `UI`, 및 `UI` 에 따라 달라 집니다 `Dsl`합니다.  
  
-   에 `DslPackage` 프로젝트 `UI\DocView.cs` 에 정의 되어 있는 Windows Forms 컨트롤을 표시 하는 코드가 포함는 `UI` 프로젝트입니다.  
  
-   `UI` 프로젝트는 DSL에 바인딩된 폼 컨트롤의 작업 예제를 포함 합니다. 그러나 DSL 정의 변경 된 경우 작동 하지 않습니다. `UI` 프로젝트에 포함 되어 있습니다.  
  
    -   라는 Windows Forms 클래스 `ModelViewControl`합니다.  
  
    -   라는 파일을 `DataBinding.cs` 의 추가 부분 정의 포함 하는 `ModelViewControl`합니다. 해당 콘텐츠를 보려면 **솔루션 탐색기**를 파일에 대 한 바로 가기 메뉴를 열고 선택 **코드 보기**합니다.  
  
### <a name="about-the-ui-project"></a>UI 프로젝트에 대 한  
 고유한 DSL을 정의 하려면 DSL 정의 파일을 업데이트 하는 경우에 컨트롤을 업데이트 해야 합니다는 `UI` DSL을 표시 하는 프로젝트입니다. 와 달리는 `Dsl` 및 `DslPackage` 프로젝트와 샘플 `UI` 프로젝트에서 생성 되지 않습니다 `DslDefinitionl.dsl`합니다. 이 연습에서 다루지 않는 하지만 원한다 면 코드를 생성 하려면.tt 파일을 추가할 수 있습니다.  
  
## <a name="updating-the-dsl-definition"></a>DSL 정의 업데이트합니다.  
 다음 DSL 정의이 연습에서 사용 됩니다.  
  
 ![DSL-Wpf-1](~/modeling/media/dsl-wpf-1.png "DSL-Wpf-1")  
  
#### <a name="to-update-the-dsl-definition"></a>DSL 정의 업데이트 하려면  
  
1.  DSL 디자이너에서 DslDefinition.dsl을 엽니다.  
  
2.  삭제 **ExampleElement**  
  
3.  이름 바꾸기는 **ExampleModel** 도메인 클래스를 `Farm`합니다.  
  
     라는 추가 도메인 속성을 지정 `Size` 형식의 **Int32**, 및 `IsOrganic` 형식의 **부울**합니다.  
  
    > [!NOTE]
    >  루트 도메인 클래스를 삭제 하 고 다음 새로운 루트를 만들 경우 편집기 루트 클래스 속성을 다시 설정 해야 합니다. **DSL 탐색기**선택, **편집기**합니다. 그런 다음 속성 창에서 설정 **루트 클래스** 를 `Farm`합니다.  
  
4.  사용 된 **명명 된 도메인 클래스** 다음 도메인 클래스를 만드는 도구:  
  
    -   `Field`– 지정이 추가 도메인 속성인 `Size`합니다.  
  
    -   `Animal`-속성 창에서 설정 **상속 한정자** 를 **추상**합니다.  
  
5.  사용 된 **도메인 클래스** 다음 클래스를 만드는 도구:  
  
    -   `Sheep`  
  
    -   `Goat`  
  
6.  사용 된 **상속** 도구를 `Goat` 및 `Sheep` 에서 상속 `Animal`합니다.  
  
7.  사용 하는 **포함** 포함 하는 도구 `Field` 및 `Animal` 아래 `Farm`합니다.  
  
8.  다이어그램을 정리 하는 데 좋습니다. 중복 된 요소 수를 줄이기 위해 사용 하 여는 **여기에 하위 트리 가져오기** 리프 요소의 바로 가기 메뉴에서 명령입니다.  
  
9. **모든 템플릿 변환** 솔루션 탐색기의 도구 모음에서입니다.  
  
10. 빌드는 **Dsl** 프로젝트입니다.  
  
    > [!NOTE]
    >  이 단계에서 다른 프로젝트를 오류 없이 작성 하지 않습니다. 그러나 해당 어셈블리를 데이터 원본 마법사를 사용할 수 있도록 Dsl 프로젝트를 작성 하려고 합니다.  
  
## <a name="updating-the-ui-project"></a>UI 프로젝트를 업데이트합니다.  
 이제는 DSL 모델에 저장 된 정보를 표시 하는 새 사용자 정의 컨트롤을 만들 수 있습니다. 모델에 사용자 정의 컨트롤을 연결 하는 가장 쉬운 방법은 데이터 바인딩을 통해 됩니다. 데이터 바인딩 이라는 어댑터 유형을 **ModelingBindingSource** Dsl VMSDK 아닌 인터페이스에 연결 하도록 설계 된.  
  
#### <a name="to-define-your-dsl-model-as-a-data-source"></a>데이터 원본으로 DSL 모델을 정의 하려면  
  
1.  에 **데이터** 메뉴 선택 **데이터 소스 표시**합니다.  
  
     **데이터 원본** 창이 열립니다.  
  
     선택 **새 데이터 소스 추가**합니다. **데이터 소스 구성 마법사** 열립니다.  
  
2.  선택 **개체**, **다음**합니다.  
  
     확장 **Dsl**, **Company.FarmApp**를 선택 하 고 **팜**,이 모델의 루트 클래스입니다. 선택 **마침**합니다.  
  
     솔루션 탐색기에서는 **UI** 이제 프로젝트에 포함 되어 **Properties\DataSources\Farm.datasource**  
  
     모델 클래스의 관계와 속성은 데이터 소스 창에 나타납니다.  
  
     ![DslWpf&3;](~/modeling/media/dslwpf-3.png "DslWpf-3")  
  
#### <a name="to-connect-your-model-to-a-form"></a>폼에 모델에 연결 하려면  
  
1.  에 **UI** 프로젝트에서 기존의 모든.cs 파일을 삭제 합니다.  
  
2.  새 추가 **사용자 정의 컨트롤** 라는 파일 `FarmControl` 에 **UI** 프로젝트입니다.  
  
3.  에 **데이터 원본** 드롭 다운 메뉴에서 창 **팜**, 선택 **세부 정보**합니다.  
  
     다른 속성에 대 한 기본 설정을 그대로 둡니다.  
  
4.  디자인 뷰에서 FarmControl.cs를 엽니다.  
  
     끌기 **팜** FarmControl에 데이터 소스 창에서.  
  
     다양 한 컨트롤 나타나고, 각 속성에 대 한 관계 속성 컨트롤을 생성 하지 않습니다.  
  
5.  삭제 **farmBindingNavigator**합니다. 이 자동으로 생성 된 `FarmControl` 디자이너를 만들었지만이 응용 프로그램에 유용 하지 않습니다.  
  
6.  두 인스턴스를 만드는 도구 상자를 사용 하 여 **DataGridView**, 이름을 `AnimalGridView` 및 `FieldGridView`합니다.  
  
    > [!NOTE]
    >  컨트롤에 데이터 소스 창에서 동물 및 필드 항목을 끌어 하는 대체 단계가입니다. 이 작업에는 자동으로 데이터 표 및 그리드 보기와 데이터 원본 간의 바인딩을 만듭니다. 그러나이 바인딩 Dsl에 대 한 제대로 작동 하지 않습니다. 데이터 표 및 바인딩을 만드는 것이 더 좋습니다 않으므로 수동으로.  
  
7.  도구 상자에 없는 경우는 **ModelingBindingSource** 도구를 추가 합니다. 바로 가기 메뉴는 **데이터** 탭에서 선택 **항목 선택**합니다. 에 **도구 상자 항목 선택** 대화 상자에서 **ModelingBindingSource** 에서 **.NET Framework 탭**합니다.  
  
8.  두 인스턴스를 만드는 도구 상자를 사용 하 여 **ModelingBindingSource**, 이름을 `AnimalBinding` 및 `FieldBinding`합니다.  
  
9. 설정의 **DataSource** 각 속성 **ModelingBindingSource** 를 **farmBindingSource**합니다.  
  
     설정의 **DataMember** 속성을 **동물** 또는 **필드**합니다.  
  
10. 설정의 **데이터 원본** 의 속성 `AnimalGridView` 를 `AnimalBinding`, 및의 `FieldGridView` 를 `FieldBinding`합니다.  
  
11. 사용자 취향을 팜 컨트롤의 레이아웃을 조정 합니다.  
  
 **ModelingBindingSource** 는 Dsl에 관련 된 몇 가지 기능을 수행 하는 어댑터:  
  
-   VMSDK 저장소 트랜잭션에서 업데이트를 래핑합니다.  
  
     예를 들어 그리드 보기에서에서 행을 삭제 하는 사용자 때 일반 바인딩 결과적으로 트랜잭션 예외가 발생에서 됩니다.  
  
-   사용자가 행을 선택 하면 속성 창 데이터 표 행으로 하는 대신 해당 모델 요소의 속성을 표시, 되도록 조정 합니다.  
  
 ![DslWpf4](~/modeling/media/dslwpf4.png "DslWpf4")  
데이터 원본 및 뷰 간 링크의 스키마입니다.  
  
#### <a name="to-complete-the-bindings-to-the-dsl"></a>DSL에 대 한 바인딩을 완료 하려면  
  
1.  다음 코드를 별도 코드 파일에 추가 된 **UI** 프로젝트:  
  
    ```c#  
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
  
2.  에 **DslPackage** 프로젝트에서 편집 **DslPackage\DocView.tt** 다음 변수 정의를 업데이트 합니다.  
  
    ```c#  
    string viewControlTypeName = "FarmControl";  
    ```  
  
## <a name="testing-the-dsl"></a>DSL을 테스트  
 이제 DSL 솔루션 빌드하고 나중에 추가할 추가 개선 하려는 수 있지만 실행할 수 있습니다.  
  
#### <a name="to-test-the-dsl"></a>DSL을 테스트 하려면  
  
1.  솔루션을 빌드하고 실행합니다.  
  
2.  Visual Studio의 실험적 인스턴스를 열고는 **샘플** 파일입니다.  
  
3.  에 **FarmApp 탐색기**에 바로 가기 메뉴를 열고는 **팜** 루트 노드를 선택한 **새 염소 추가**합니다.  
  
     `Goat1`에 표시 된 **동물** 보기.  
  
    > [!WARNING]
    >  바로 가기 메뉴를 사용 해야는 **팜** 노드를 하지는 **동물** 노드.  
  
4.  선택 된 **팜** 루트 노드 및 해당 속성을 확인 합니다.  
  
     폼 보기에서 변경 된 **이름** 또는 **크기** 팜의 합니다.  
  
     때 속성 창에서 해당 속성 변경 내용 폼의 각 필드에서 멀리 이동 합니다.  
  
## <a name="enhancing-the-dsl"></a>DSL 향상  
  
#### <a name="to-make-the-properties-update-immediately"></a>즉시 업데이트 속성  
  
1.  FarmControl.cs의 디자인 뷰에서 단순 필드 이름, 크기 또는 IsOrganic 등을 선택 합니다.  
  
2.  속성 창에서 확장 **데이터 바인딩** 열리고 **(고급)**합니다.  
  
     에 **서식 지정 및 고급 바인딩** 대화 상자에서 **데이터 소스 업데이트 모드**, 선택 **OnPropertyChanged**합니다.  
  
3.  솔루션을 빌드하고 실행합니다.  
  
     팜 모델 변경 내용 즉시의 해당 속성 필드의 콘텐츠를 변경 하면 있는지를 확인 합니다.  
  
#### <a name="to-provide-add-buttons"></a>추가 단추를 제공 하려면  
  
1.  FarmControl.cs의 디자인 뷰에서 폼에 단추를 만들려면 도구 상자를 사용 합니다.  
  
     이름 및 해당 단추의 텍스트를 예를 들어 편집 `New Sheep`합니다.  
  
2.  단추 내부의 코드 (예를 들어 두 번 클릭)에서 엽니다.  
  
     다음과 같이 편집 합니다.  
  
    ```c#  
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
  
    ```c#  
  
    using Microsoft.VisualStudio.Modeling;  
  
    ```  
  
3.  염소 및 필드에 대 한 비슷한 단추를 추가 합니다.  
  
4.  솔루션을 빌드하고 실행합니다.  
  
5.  새로 만들기 단추 항목을 추가 확인 합니다. 새 항목 FarmApp 탐색기에서 및 해당 하는 데이터 그리드 보기에 표시 됩니다.  
  
     데이터 그리드 보기의 요소 이름을 편집할 수 있습니다. 여기에서 삭제할 수 있습니다.  
  
 ![DSL-Wpf-2](~/modeling/media/dsl-wpf-2.png "DSL-Wpf-2")  
  
### <a name="about-the-code-to-add-an-element"></a>요소를 추가 하는 코드에 대 한  
 새 요소 단추에 대 한 다음 대체 코드는 약간 더 간단 합니다.  
  
```c#  
private void NewSheepButton_Click(object sender, EventArgs e)  
{  
  using (Transaction t = farm.Store.TransactionManager.BeginTransaction("Add sheep"))  
  {  
    farm.Animals.Add(new Sheep(farm.Partition)); ;  
    t.Commit();  
  }  
}  
  
```  
  
 그러나이 코드는 새 항목에 대 한 기본 이름을 설정 하지 않습니다. 에 정의 된 모든 사용자 지정 된 병합 실행 되지 않는 **요소 병합 지시문** 는 DSL의 정의 된 모든 사용자 지정 병합 코드가 실행 되지 않습니다.  
  
 사용 하는 권장 따라서 <xref:Microsoft.VisualStudio.Modeling.ElementOperations>새 요소를 만듭니다.</xref:Microsoft.VisualStudio.Modeling.ElementOperations> 자세한 내용은 참조 [사용자 지정 요소 만들기 및 이동](../modeling/customizing-element-creation-and-movement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도메인별 언어를 정의 하는 방법](../modeling/how-to-define-a-domain-specific-language.md)   
 [도메인별 언어 사용자 지정 하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)   
 [Visual Studio용 모델링 SDK - 도메인별 언어](../modeling/modeling-sdk-for-visual-studio-domain-specific-languages.md)
