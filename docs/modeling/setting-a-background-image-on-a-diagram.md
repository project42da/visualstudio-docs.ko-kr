---
title: "다이어그램에 배경 이미지 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e334a24c-8521-4072-b50f-e59158dde145
caps.latest.revision: 2
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 2
---
# 다이어그램에 배경 이미지 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK에서는 사용자 지정 코드를 사용하여 생성된 디자이너의 배경 이미지를 설정할 수 있습니다.  
  
## 배경 이미지 설정  
  
#### 생성된 디자이너의 배경 이미지를 설정하려면  
  
1.  다이어그램 배경으로 사용할 이미지 파일을 현재 프로젝트의 Dsl\\Resources 디렉터리에 복사합니다.  
  
2.  **솔루션 탐색기**에서 Dsl\\Resources 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **기존 항목**을 클릭합니다.  
  
3.  **기존 항목 추가** 대화 상자에서 Dsl\\Resources 폴더를 찾습니다.  
  
4.  **파일 형식** 목록에서 **이미지 파일**을 선택합니다.  
  
5.  디렉터리에 복사한 이미지 파일을 클릭하고 **추가**를 클릭합니다.  
  
6.  Dsl을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭하여 Dsl 프로젝트 속성을 엽니다.  
  
7.  **리소스** 탭에서 **이 프로젝트에는 기본 리소스 파일이 없습니다. 기본 리소스 파일을 만들려면 여기를 클릭하십시오.**를 클릭합니다.  
  
8.  그림을 **솔루션 탐색기**에서 리소스 창으로 끌어 이미지 파일을 리소스 파일에 추가합니다.  
  
9. 파일 메뉴를 열고 프로젝트 속성을 저장할 옵션을 클릭합니다.  
  
10. Dsl\\Properties\\Resources.resx 파일이 있으며 그 아래에 Resources.Designer.cs 파일이 있는지 확인합니다.  
  
11. Resources.Designer.cs가 없으면 **솔루션 탐색기**에서 Resources.resx 파일을 클릭합니다.  
  
12. **속성** 창에서 `Custom Tool` 속성을 `ResXFileCodeGenerator`로 설정합니다.  
  
13. **솔루션 탐색기**에서 Dsl 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 폴더**를 선택합니다.  
  
14. 폴더 이름을 Custom으로 지정합니다.  
  
15. Custom 폴더를 마우스 오른쪽 단추로 클릭하고 **추가**를 가리킨 다음 **새 항목**을 클릭합니다.  
  
16. **새 항목 추가** 대화 상자의 **템플릿** 목록에서 **코드 파일**을 클릭합니다.  
  
17. **이름** 상자에 `BackgroundImage.cs`를 입력한 다음 **추가**를 클릭합니다.  
  
18. 네임스페이스, 다이어그램 클래스 이름 및 이미지 파일 리소스 이름을 조정하여 다음 코드를 BackgroundImage.cs 파일에 복사합니다.  
  
     "MyDiagramClass"는 Dsl\\GeneratedCode\\Diagrams.cs에 정의된 다이어그램 partial 클래스의 이름으로 바꿉니다.  Dsl\\GeneratedCode\\Diagrams.cs 파일에서 정확한 네임스페이스를 검색할 수도 있습니다.  
  
    ```  
    using System;  
    using Microsoft.VisualStudio.Modeling.Diagrams;  
  
    // Fix the namespace:  
    namespace Fabrikam.MyLanguage  
    {  
      // Fix the Diagram Class name - get it from GeneratedCode\Diagram.cs  
  
      public partial class Language29Diagram  
      {  
        protected override void InitializeInstanceResources()  
        {  
          // Fix the Resources namespace and the Image resource name:  
          ImageField backgroundField = new ImageField("background",  
              Fabrikam.MyLanguage.Properties.Resources.MyPicture);  
  
          backgroundField.DefaultFocusable = false;  
          backgroundField.DefaultSelectable = false;  
          backgroundField.DefaultVisibility = true;  
          backgroundField.DefaultUnscaled = false;  
  
          shapeFields.Add(backgroundField);  
  
          backgroundField.AnchoringBehavior  
            .SetTopAnchor(AnchoringBehavior.Edge.Top, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetLeftAnchor(AnchoringBehavior.Edge.Left, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetRightAnchor(AnchoringBehavior.Edge.Right, 0.01);  
          backgroundField.AnchoringBehavior  
            .SetBottomAnchor(AnchoringBehavior.Edge.Bottom, 0.01);  
  
          base.InitializeInstanceResources();  
        }  
      }  
    }  
    ```  
  
     프로그램 코드를 사용하여 모델을 사용자 지정하는 방법은 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)를 참조하세요.  
  
## 참고 항목  
 [모양 및 연결선 정의](../modeling/defining-shapes-and-connectors.md)   
 [텍스트 및 이미지 필드 사용자 지정](../modeling/customizing-text-and-image-fields.md)   
 [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도메인별 언어 사용자 지정 하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)