---
title: "다이어그램에는 배경 이미지 설정과 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e334a24c-8521-4072-b50f-e59158dde145
caps.latest.revision: "2"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: 13e52e30ebeda4d881474bcf990068d1a92bb7f4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setting-a-background-image-on-a-diagram"></a>다이어그램에 배경 이미지 설정
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Visualization and Modeling SDK에서는 사용자 지정 코드를 사용하여 생성된 디자이너의 배경 이미지를 설정할 수 있습니다.  
  
## <a name="setting-the-background-image"></a>배경 이미지 설정  
  
#### <a name="to-set-a-background-image-for-a-generated-designer"></a>생성된 디자이너의 배경 이미지를 설정하려면  
  
1.  다이어그램 배경으로 사용할 이미지 파일을 현재 프로젝트의 Dsl\Resources 디렉터리에 복사합니다.  
  
2.  **솔루션 탐색기**Dsl\Resources 폴더를 마우스 오른쪽 단추로 가리킨 **추가**, 클릭 하 고 **기존 항목**합니다.  
  
3.  에 **기존 항목 추가** 대화 상자 Dsl\Resources 폴더를 찾습니다.  
  
4.  에 **파일 형식** 목록에서 클릭 **이미지 파일**합니다.  
  
5.  디렉터리에 복사 되는 이미지 파일을 클릭 한 다음 클릭 **추가**합니다.  
  
6.  Dsl를 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성** Dsl 프로젝트의 속성을 엽니다.  
  
7.  에 **리소스** 탭을 클릭 **이 프로젝트는 기본 리소스 파일 포함 되어 있지 않습니다. 기본 리소스 파일을 만들려면 여기를 클릭하십시오.**를 클릭합니다.  
  
8.  해당 이미지 파일을 리소스 파일에서 그림을 끌어 추가 **솔루션 탐색기** 리소스 창에 있습니다.  
  
9. 파일 메뉴를 열고 프로젝트 속성을 저장할 옵션을 클릭합니다.  
  
10. Dsl\Properties\Resources.resx 파일이 있으며 그 아래에 Resources.Designer.cs 파일이 있는지 확인합니다.  
  
11. Resources.Designer.cs 누락 되 면 클릭 Resources.resx 파일에서 **솔루션 탐색기**합니다.  
  
12. 에 **속성** 창에서 설정 된 `Custom Tool` 속성을 `ResXFileCodeGenerator`합니다.  
  
13. **솔루션 탐색기**Dsl 프로젝트를 마우스 오른쪽 단추로 가리킨 **추가**를 클릭 하 고 **새 폴더**합니다.  
  
14. 폴더 이름을 **사용자 지정**합니다.  
  
15. 사용자 지정 폴더를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**를 클릭 하 고 **새 항목**합니다.  
  
16. 에 **새 항목 추가** 대화 상자는 **템플릿** 목록에서 클릭 **코드 파일**합니다.  
  
17. 에 **이름** 상자에 입력 합니다 `BackgroundImage.cs`를 클릭 하 고 **추가**합니다.  
  
18. 네임스페이스, 다이어그램 클래스 이름 및 이미지 파일 리소스 이름을 조정하여 다음 코드를 BackgroundImage.cs 파일에 복사합니다.  
  
     "MyDiagramClass"는 Dsl\GeneratedCode\Diagrams.cs에 정의된 다이어그램 partial 클래스의 이름으로 바꿉니다. Dsl\GeneratedCode\Diagrams.cs 파일에서 정확한 네임스페이스를 검색할 수도 있습니다.  
  
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
  
     프로그램 코드를 사용 하 여 모델을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [셰이프 및 연결선을 정의합니다.](../modeling/defining-shapes-and-connectors.md)   
 [텍스트 및 이미지 필드를 사용자 지정](../modeling/customizing-text-and-image-fields.md)   
 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)
 
[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
