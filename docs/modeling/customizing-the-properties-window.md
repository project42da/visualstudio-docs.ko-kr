---
title: "속성 창 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 속성 창"
ms.assetid: b6658de5-4e85-4628-93b2-5cc12f63d25b
caps.latest.revision: 20
caps.handback.revision: 20
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# 속성 창 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

사용자의 모양 및 동작 속성 창의 사용자 도메인 관련 언어 \(DSL\)에 지정할 수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  DSL 정의에 각 도메인 클래스의 도메인 등록 정보를 정의합니다.  또는 모델 탐색기에서 다이어그램에서 클래스의 인스턴스를 선택 하면 기본적으로 모든 도메인 속성을 속성 창에 나열 됩니다.  이 다이어그램에서 셰이프 필드에 매핑하지 없습니다 경우에 도메인 속성 값을 편집할 수 있습니다.  
  
## 이름, 설명 및 종류  
 **표시 이름**.  사용자 정의 도메인 속성에서 속성의 표시 이름을 런타임 시 속성 창에 표시 되는 이름입니다.  그러나 속성을 업데이트 하는 프로그램 코드를 작성할 때 이름이 사용 됩니다.  이름은 올바른 CLR 영숫자 이름을 해야 합니다 있지만 표시 이름은 공백을 포함할 수 있습니다.  
  
 DSL 정의에 있는 속성의 이름을 설정 하는 경우의 표시 이름 이름의 복사본을 자동으로 설정 됩니다.  파스칼 cased 이름을 "FuelGauge"와 같이 작성 하는 경우에 공백 표시 이름을 자동으로 포함 됩니다: "연료 게이지".  그러나 사용자의 표시 이름을 명시적으로 다른 값으로 설정할 수 있습니다.  
  
 **설명**.  도메인 속성에 대 한 두 개의 위치에 표시 됩니다.  
  
-   사용자 속성을 선택 하면 속성 창의 아래쪽에서.  속성이 무엇을 나타내는지 사용자에 게 설명할 수 있습니다.  
  
-   생성 된 프로그램 코드를 합니다.  API 설명서를 추출할 설명서 기능을 사용 하는 경우 API에서이 속성에 대 한 설명으로 표시 됩니다.  
  
 **범주**.  범주 속성 창의 제목입니다.  
  
## 스타일 기능을 노출합니다.  
 동적 기능 그래픽 요소를 표시할 수 있습니다 또는  *노출* 로 도메인 등록 정보입니다.  사용자가이 이런 식으로 노출 된 기능을 업데이트할 수 있습니다와 자세한 내용을 쉽게 프로그램 코드를 통해 업데이트할 수 있습니다.  
  
 DSL 정의에서 클래스 셰이프를 마우스 오른쪽 단추로 클릭 하 고  **추가 노출**, 다음 기능을 선택 합니다.  
  
 셰이프를 노출할 수 있는  **FillColor**,  **OutlineColor**,  **TextColor**,  **OutlineDashStyle**,  **OutlineThickness** 및  **FillGradientMode** 속성입니다.  커넥터에 노출할 수 있는  **색**`,`**TextColor**,  **DashStyle**, 및  **두께** 속성입니다.  다이어그램에서 노출할 수 있는  **FillColor** 및  **TextColor** 속성입니다.  
  
## 관련된 요소의 속성을 표시 하는 전달 합니다.  
 DSL의 사용자가 모델에서 요소를 선택 하면 해당 요소의 속성이 속성 창에 표시 됩니다.  그러나 지정 된 관련된 요소의 속성을 표시할 수도 있습니다.  함께 작동 하는 요소 그룹을 정의 하는 경우에 유용 합니다.  예를 들어, 주 요소와 선택적 플러그인 요소를 정의할 수 있습니다.  기본 요소에 매핑되는 경우 다른 요소 하나에 있는 것 처럼 해당 속성을 모두 볼 수 유용 합니다.  
  
 이 효과 라고  *속성 전달*, 및 여러 사례에서 자동으로 발생 합니다.  다른 경우에는 도메인 형식 설명자를 정의 하 여 전달 하는 속성을 얻을 수 있습니다.  
  
### 기본 속성 전달 사례  
 셰이프 또는 연결선 또는 요소 탐색기에서 사용자를 선택 하는 경우 다음 속성을 속성 창에 표시 됩니다.  
  
-   도메인 모델 요소를 포함 하는 기본 클래스에 정의 된 클래스에 정의 된 도메인 속성입니다.  도메인 등록 정보에 설정 된 경우는 예외입니다  **는 찾아볼 수** 에 `False`.  
  
-   0에서 1까지의 복합성을 가진 관계를 통해 연결 된 요소의 이름입니다.  커넥터 매핑 관계를 정의 하지 않은 경우에 요소를 선택적으로 볼 수 있는 편리한 방법을 연결을 제공 합니다.  
  
-   도메인 속성 요소를 대상으로 하는 포함 관계입니다.  포함 관계 일반적으로 명시적으로 표시 되기 때문에 사용자가 해당 속성을 볼 수 있습니다.  
  
-   선택한 셰이프 또는 연결선에 정의 된 도메인 속성입니다.  
  
### 추가 속성 전달  
 속성을 전달 하기 위해 도메인 형식 설명자를 정의 합니다.  도메인 두 도메인 클래스 간의 관계를 있으면 도메인 형식 설명자 두 번째 도메인 클래스는 도메인 속성 값을 첫 번째 클래스에서 도메인 속성을 설정할 수 있습니다.  예를 들어, 책 도메인 클래스와는 작성자 도메인 클래스 간의 관계가 있으면 도메인 형식 설명자 책을 선택할 때 속성 창에 나타나는 Name 속성의 책의 저자 합니다 사용할 수 있습니다.  
  
> [!NOTE]
>  사용자가 모델을 편집할 때 속성 창을 속성 전달에 영향을 줍니다.  받는 클래스의 도메인 속성을 정의 하지 않습니다.  DSL 정의의 다른 부분에서 또는 프로그램 코드에 전달 된 도메인 속성에 액세스 하려면 전달 요소에 액세스 해야 합니다.  
  
 다음 절차는 DSL을 만들었다고 가정 합니다.  필수 구성 요소가 처음 몇 단계를 요약합니다.  
  
##### 속성에서 다른 요소를 전달  
  
1.  만들기는 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] 이은 책과 저자 라고 두 개 이상의 클래스를 포함 하는 솔루션입니다.  책과 저자 사이의 어떤 종류의 관계가 있어야 합니다.  
  
     작성자의 책을 가질 수 있도록 소스 \(북 쪽 역할\) 역할의 복합성은 0에서 1까지 또는 1에서 해야 합니다.  
  
2.  **DSL 탐색기**Book 도메인 클래스를 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **새 DomainTypeDescriptor를 추가**.  
  
     명명 된 노드  **사용자 지정 속성 설명자를 경로** 표시를  **사용자 지정 형식 설명자** 노드.  
  
3.  마우스는  **사용자 지정 형식 설명자** 노드를 클릭 하 고  **추가 새 PropertyPath**.  
  
     새 속성 경로에서 표시 되는  **사용자 지정 속성 설명자를 경로** 노드.  
  
4.  새 속성 경로 선택 하에  **속성** 창 설정  **경로 속성에** 적절 한 모델 요소의 경로.  
  
     이 속성의 오른쪽에 있는 아래쪽 화살표를 클릭 하 여 경로 트리 보기에서 편집할 수 있습니다.  도메인 경로 대 한 자세한 내용은 참조 하십시오. [도메인 경로 구문](../modeling/domain-path-syntax.md).  이 작업을 편집한 경우 경로 유사 합니다  **BookReferencesAuthor.Author\/\!저자**.  
  
5.  설정  **속성** 에 있는 **Name** 작성자의 도메인 속성을 합니다.  
  
6.  설정  **표시 이름** 만든이 이름입니다.  
  
7.  모든 템플릿 변환 하 고, 작성 하 고, DSL을 실행 합니다.  
  
8.  모델 다이어그램에서 저자는 책을 만들어 참조 관계를 사용 하 여 연결 합니다.  Book 요소를 선택 하 고 속성 창에서 속성을 책에 저자 이름이 표시 되어야 합니다.  연결 된 만든이 이름을 변경 하거나 책을 다른 만든이에 연결 하 고 북 작성자 이름이 바뀝니다.  
  
## 사용자 지정 속성 편집기  
 속성 창은 편집 환경 각 도메인 속성의 형식에 대 한 적절 한 기본값을 제공 합니다.  예를 들어, 열거 형식에 대 한 사용자 드롭다운 목록에 표시 되 고 숫자 속성에 대 한 사용자 숫자를 입력할 수 있습니다.  이 기본 제공 형식에 적용 됩니다.  외부 형식에서 지정 하는 경우 사용자 속성의 값을 볼 수 있지만 편집할 수 있습니다.  
  
 그러나 다음 편집기 및 형식 지정할 수 있습니다.  
  
1.  다른 편집기를 표준 형식으로 사용 됩니다.  예를 들어, 문자열 속성에 대 한 파일 경로 편집기를 지정할 수 있습니다.  
  
2.  도메인 속성 및이 대 한 편집기는 외부 형식입니다.  
  
3.  A입니다.NET 편집기 파일 경로 편집기 같은 고유한 사용자 지정 속성 편집기를 만들 수 있습니다.  
  
     외부 형식과 문자열 기본 편집기가 같은 형식의 사이 변환 합니다.  
  
 DSL에  *외부 형식* 간단한 형식 \(예: Boolean, Int32\) 또는 문자열 중 하나가 아닌 모든 종류입니다.  
  
#### 외부 형식이 도메인 속성을 정의 하려면  
  
1.  **솔루션 탐색기**, 외부 형식에 포함 된 어셈블리 \(DLL\)에 대 한 참조 추가 **Dsl** 프로젝트.  
  
     어셈블리가 될 수는 있습니다.NET 어셈블리 또는 어셈블리가 제공 합니다.  
  
2.  추가 입력 하는  **도메인 유형** 아직 수행 하지 않는 한 목록.  
  
    1.  Dsldefinition.dsl를 열고 및  **DSL 탐색기**에서 루트 노드를 마우스 오른쪽 단추로 클릭 하 고 다음을 클릭  **추가 새 외부 형식**.  
  
         새 항목 표시는  **도메인 유형** 노드.  
  
        > [!WARNING]
        >  메뉴 항목에서 DSL 루트 노드를 아닙니다의  **도메인 종류** 노드.  
  
    2.  속성 창에서 이름 및 새 형식의 네임 스페이스를 설정 합니다.  
  
3.  도메인 속성을 도메인 클래스에는 통상적인 방법으로 추가 합니다.  
  
     속성 창에서 외부 형식 드롭다운 목록에서 선택은  **형식** 필드입니다.  
  
 이 단계에서 사용자의 속성 값을 볼 수 있지만 편집할 수 없습니다.  표시 된 값을 얻을 수 있는 `ToString()` 함수입니다.  명령 또는 규칙의 예를 들어 속성의 값을 설정 하는 프로그램 코드를 작성할 수 있습니다.  
  
### 속성 편집기를 설정합니다.  
 Domain 속성에 다음과 같은 형식으로 CLR 특성을 추가 합니다.  
  
```  
[System.ComponentModel.Editor (  
   typeof(AnEditor),  
   typeof(System.Drawing.Design.UITypeEditor))]  
  
```  
  
 사용 하 여 특성에 대 한 속성을 설정할 수 있습니다에서  **사용자 지정 특성** 항목 속성 창에서.  
  
 종류를 `AnEditor` 의 두 번째 매개 변수에 지정 된 형식에서 파생 되어야 합니다.  두 번째 매개 변수 하나가 있어야 <xref:System.Drawing.Design.UITypeEditor> 또는 <xref:System.ComponentModel.ComponentEditor>.  자세한 내용은 <xref:System.ComponentModel.EditorAttribute>를 참조하십시오.  
  
 사용자 편집기 또는에서 제공 된 편집기를 지정할 수 있습니다에서 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 같은 <xref:System.Windows.Forms.Design.FileNameEditor> 또는 <xref:System.Drawing.Design.ImageEditor>.  예를 들어, 다음 절차를 따르십시오 속성에 사용자 파일 이름을 입력할 수 있습니다.  
  
##### 파일 이름을 도메인 속성을 정의 하려면  
  
1.  도메인 속성 도메인 클래스는 DSL 정의 추가 합니다.  
  
2.  새 속성을 선택 합니다.  에 있는  **사용자 지정 특성** 필드 속성 창에서 다음 속성을 입력 합니다.  이 특성을 입력 하려면 줄임표를 클릭  **\[...\]** 다음 특성 이름 및 매개 변수를 개별적으로 입력 합니다.  
  
    ```  
    [System.ComponentModel.Editor (  
       typeof(System.Windows.Forms.Design.FileNameEditor)  
       , typeof(System.Drawing.Design.UITypeEditor))]  
  
    ```  
  
3.  Domain 속성의 기본 설정에 두어  **문자열**.  
  
4.  편집기를 테스트 하려면 사용자가 도메인 속성을 편집 하려면 파일 이름을 편집기를 열 수 있는지 확인 합니다.  
  
    1.  F5 키 또는 CTRL \+ f 5를 누릅니다.  디버깅 솔루션에 테스트 파일을 엽니다.  도메인 클래스의 요소를 만들고이 선택 합니다.  
  
    2.  속성 창에서 도메인 속성을 선택 합니다.  값 필드에서 줄임표 \(...\)를 보여 줍니다.  **\[...\]**.  
  
    3.  줄임표를 클릭합니다.  파일 대화 상자가 나타납니다.  파일을 선택 하 고 대화 상자를 닫습니다.  파일 경로 이제 domain 속성의 값입니다.  
  
### 사용자 고유의 속성 편집기를 정의합니다.  
 편집기를 직접 정의할 수 있습니다.  이렇게 사용자 정의 된 형식을 편집 하거나 특별 하 게 표준 형식을 편집 하려면 허용 하도록 합니다.  예를 들어, 사용자가 입력 하는 수식을 나타내는 string을 수 있습니다.  
  
 파생 되는 클래스를 작성 하 여 편집기를 정의 <xref:System.Drawing.Design.UITypeEditor>.  클래스를 재정의 해야 합니다.  
  
-   <xref:System.Drawing.Design.UITypeEditor.EditValue%2A>사용자와 상호 작용 하는 속성 값을 업데이트 합니다.  
  
-   <xref:System.Drawing.Design.UITypeEditor.GetEditStyle%2A>편집기 대화 상자를 열거나 드롭 다운 메뉴를 제공 됩니다 여부를 지정 합니다.  
  
 속성 표에 표시 되는 속성 값의 그래픽 표현을 제공할 수도 있습니다.  이렇게 하려면 재정의 `GetPaintValueSupported`, 및 `PaintValue`.  자세한 내용은 <xref:System.Drawing.Design.UITypeEditor>를 참조하십시오.  
  
> [!NOTE]
>  에 코드를 추가 하 여 별도 코드 파일에 **Dsl** 프로젝트.  
  
 예를 들면 다음과 같습니다.  
  
```  
internal class TextFileNameEditor : System.Windows.Forms.Design.FileNameEditor  
{  
  protected override void InitializeDialog(System.Windows.Forms.OpenFileDialog openFileDialog)  
  {  
    base.InitializeDialog(openFileDialog);  
    openFileDialog.Filter = "Text files(*.txt)|*.txt|All files (*.*)|*.*";  
    openFileDialog.Title = "Select a text file";  
  }  
}  
  
```  
  
 이 편집기를 사용 하려면 설정에서  **사용자 지정 특성** 의 도메인 속성을:  
  
```  
[System.ComponentModel.Editor (  
   typeof(MyNamespace.TextFileNameEditor)  
   , typeof(System.Drawing.Design.UITypeEditor))]  
  
```  
  
 자세한 내용은 <xref:System.Drawing.Design.UITypeEditor>를 참조하십시오.  
  
## 값의 드롭다운 목록을 제공합니다.  
 선택할 수 있는 사용자에 대 한 값 목록을 제공할 수 있습니다.  
  
> [!NOTE]
>  이 방법은 런타임에 변경할 수 있는 값 목록을 제공 합니다.  변경 되지 않는 목록을 제공 하는 경우를 고려 중인 도메인 속성 유형으로 열거 형식을 사용 하 여.  
  
 표준 값의 목록을 정의 하는 CLR 특성을 도메인 속성에 추가 합니다.  
  
```  
[System.ComponentModel.TypeConverter   
(typeof(MyTypeConverter))]  
  
```  
  
 <xref:System.ComponentModel.TypeConverter>에서 파생되는 클래스를 정의합니다.  코드를 추가 하 여 별도 파일에 **Dsl** 프로젝트입니다.  예를 들면 다음과 같습니다.  
  
```c#  
/// <summary>  
/// Type converter that provides a list of values   
/// to be displayed in the property grid.  
/// </summary>  
/// <remarks>This type converter returns a list   
/// of the names of all "ExampleElements" in the   
/// current store.</remarks>  
public class MyTypeConverter : System.ComponentModel.TypeConverter  
{  
  /// <summary>  
  /// Return true to indicate that we return a list of values to choose from  
  /// </summary>  
  /// <param name="context"></param>  
  public override bool GetStandardValuesSupported  
    (System.ComponentModel.ITypeDescriptorContext context)  
  {  
    return true;  
  }  
  
  /// <summary>  
  /// Returns true to indicate that the user has   
  /// to select a value from the list  
  /// </summary>  
  /// <param name="context"></param>  
  /// <returns>If we returned false, the user would   
  /// be able to either select a value from   
  /// the list or type in a value that is not in the list.</returns>  
  public override bool GetStandardValuesExclusive  
      (System.ComponentModel.ITypeDescriptorContext context)  
  {  
    return true;  
  }  
  
  /// <summary>  
  /// Return a list of the values to display in the grid  
  /// </summary>  
  /// <param name="context"></param>  
  /// <returns>A list of values the user can choose from</returns>  
  public override StandardValuesCollection GetStandardValues  
      (System.ComponentModel.ITypeDescriptorContext context)  
  {  
    // Try to get a store from the current context  
    // "context.Instance"  returns the element(s) that   
    // are currently selected i.e. whose values are being  
    // shown in the property grid.   
    // Note that the user could have selected multiple objects,   
    // in which case context.Instance will be an array.  
    Store store = GetStore(context.Instance);  
  
    List<string> values = new List<string>();  
  
    if (store != null)  
    {  
      values.AddRange(store.ElementDirectory  
        .FindElements<ExampleElement>()  
        .Select<ExampleElement, string>(e =>   
      {  
        return e.Name;  
      }));  
    }  
    return new StandardValuesCollection(values);  
  }  
  
  /// <summary>  
  /// Attempts to get to a store from the currently selected object(s)  
  /// in the property grid.  
  /// </summary>  
  private Store GetStore(object gridSelection)  
  {  
    // We assume that "instance" will either be a single model element, or   
    // an array of model elements (if multiple items are selected).  
  
    ModelElement currentElement = null;  
  
    object[] objects = gridSelection as object[];  
    if (objects != null && objects.Length > 0)  
    {  
      currentElement = objects[0] as ModelElement;  
    }  
    else  
    {  
        currentElement = gridSelection as ModelElement;  
    }  
  
    return (currentElement == null) ? null : currentElement.Store;  
  }  
  
}  
  
```  
  
## 참고 항목  
 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)