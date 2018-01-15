---
title: "Windows Form에 다이어그램을 포함 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c5f77fe45fd4289a442f151ff8d1174e68b353bc
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="embedding-a-diagram-in-a-windows-form"></a>Windows Forms에 다이어그램 포함
DSL 다이어그램에 표시 되는 Windows 컨트롤을 포함할 수도 있습니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 창.  
  
## <a name="embedding-a-diagram"></a>다이어그램을 포함합니다.  
  
#### <a name="to-embed-a-dsl-diagram-in-a-windows-control"></a>Windows 컨트롤에 DSL 다이어그램을 포함 하려면  
  
1.  새로 추가 **사용자 정의 컨트롤** DslPackage 프로젝트에는 파일입니다.  
  
2.  사용자 정의 컨트롤에 패널 컨트롤을 추가 합니다. 이 패널 DSL 다이어그램에 포함 됩니다.  
  
     필요한 다른 컨트롤을 추가 합니다.  
  
     컨트롤의 앵커 속성을 설정 합니다.  
  
3.  솔루션 탐색기에서 사용자 정의 컨트롤 파일을 마우스 오른쪽 단추로 클릭 하 고 클릭 **코드 보기**합니다. 코드를이 생성자 및 변수를 추가 합니다.  
  
    ```csharp  
  
    internal UserControl1(MyDSLDocView docView, Control content)  
      : this()  
    {  
      panel1.Controls.Add(content);  
      this.docView = docView;  
    }  
    private MyDSLDSLDocView docView;  
  
    ```  
  
4.  다음 내용 사용 하 여 DslPackage 프로젝트에 새 파일을 추가 합니다.  
  
    ```  
    using System.Windows.Forms;  
    namespace Company.MyDSL  
    {  
      partial class MyDSLDocView  
      {  
        private UserControl1 container;  
        public override IWin32Window Window  
        {  
          get  
          {  
            if (container == null)  
            {  
              // Put our own form inside the DSL window:  
              container = new UserControl1(this,  
                (Control)base.Window);  
            }  
            return container;  
    } } } }  
  
    ```  
  
5.  DSL를 테스트 하려면 F5 키를 누릅니다 하 고 샘플 모델 파일을 엽니다. 다이어그램이는 컨트롤 내부에 나타납니다. 도구 상자와 다른 기능이 정상적으로 작동 합니다.  
  
#### <a name="updating-the-form-using-store-events"></a>저장소 이벤트를 사용 하 여 폼을 업데이트 합니다.  
  
1.  폼 디자이너에 추가 **ListBox** 라는 `listBox1`합니다. 모델에 요소 목록이 나타납니다. Synchronism 사용 하 여 모델에에서 유지 됩니다 *이벤트 저장*합니다. 자세한 내용은 참조 [이벤트 처리기 전파 변경 내용을 바깥쪽 the 모델](../modeling/event-handlers-propagate-changes-outside-the-model.md)합니다.  
  
2.  사용자 지정 코드 파일에서 추가 메서드를 재정의 하는 문서 뷰 클래스:  
  
    ```  
  
    partial class MyDSLDocView  
    {  
     /// <summary>  
     /// Register store event listeners.  
     /// This method is called when the model and diagram    
     /// have completed loading.   
     /// </summary>  
     protected override bool LoadView()  
      {  
        bool result = base.LoadView();  
        Store store = this.DocData.Store;  
        EventManagerDirectory emd = store.EventManagerDirectory;  
        DomainClassInfo componentClass = store.DomainDataDirectory.FindDomainClass(typeof(ExampleElement));  
        emd.ElementAdded.Add(componentClass, new EventHandler<ElementAddedEventArgs>(AddElement));  
        emd.ElementDeleted.Add(componentClass, new EventHandler<ElementDeletedEventArgs>(RemoveElement));  
  
        // Do the initial parts list:  
        container.SetUpFormFromModel();  
        return result;  
      }  
     /// <summary>  
     /// Listener method called on creation of each instance of   
     /// the ExampleElement class or its subclasses.  
     /// </summary>  
     private void AddElement(object sender, ElementAddedEventArgs e)  
     {  
       container.Add(e.ModelElement as ExampleElement);  
     }  
     /// <summary>  
     /// Listener method called after deletion of each instance of   
     /// the ExampleElement class or its subclasses.  
     /// </summary>  
     private void RemoveElement(object sender, ElementDeletedEventArgs e)  
     {  
       container.Remove(e.ModelElement as ExampleElement);  
     }  
  
    ```  
  
3.  사용자 정의 컨트롤 뒤에 있는 코드에서 요소를 추가 및 제거에 대 한 수신 대기 하는 메서드를 삽입 합니다.  
  
    ```  
  
          public partial class UserControl1 : UserControl { ...  
  
    private ExampleModel modelRoot;  
  
    internal void Add(ExampleElement e) { UpdatePartsList(); }  
    internal void Remove(ExampleElement e) { UpdatePartsList(); }  
  
    internal void SetUpFormFromModel()  
    {  
      modelRoot = this.docView.CurrentDiagram.ModelElement as ExampleModel;  
      UpdatePartsList();  
    }  
  
    private void UpdatePartsList()  
    {  
      StringBuilder builder = new StringBuilder();  
      listBox1.Items.Clear();  
      foreach (ExampleElement c in modelRoot.Elements)  
      {  
        listBox1.Items.Add(c.Name);  
      }  
    }  
  
    ```  
  
4.  DSL를 테스트 하려면 F5 키를 누릅니다. 및의 실험적 인스턴스에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 샘플 모델 파일을 엽니다.  
  
     목록 상자 모델에 요소 목록이 표시 하 고이 정확한 지 모든 추가 또는 삭제 한 후 실행 취소 및 다시 실행을 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)