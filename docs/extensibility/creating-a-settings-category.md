---
title: "설정 범주 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로필 설정, 범주 만들기"
ms.assetid: 97c88693-05ff-499e-8c43-352ee073dcb7
caps.latest.revision: 39
caps.handback.revision: 39
ms.author: "gregvanl"
manager: "ghogen"
---
# 설정 범주 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 Visual Studio 설정 범주가 만들고 사용 하 여 값을 저장 하 고 설정 파일에서 값을 복원 합니다. 설정 범주는 "사용자 지정 설정 위치;"으로 표시 되는 관련 된 속성의 그룹 즉,에서 확인란으로는 **가져오기 및 내보내기 설정을** 마법사. \(에서 찾을 수는 **도구** 메뉴.\) 설정을 저장 또는 범주를 복원 하 고 개별 설정 마법사에 표시 되지 않습니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
 파생 하 여 설정 범주를 만들면는 <xref:Microsoft.VisualStudio.Shell.DialogPage> 클래스입니다.  
  
 이 연습을 시작 하려면 먼저 첫 번째 섹션을 완료 해야 [옵션 페이지 만들기](../extensibility/creating-an-options-page.md)합니다. 결과 옵션 속성 표를 사용 하 여 검토 하 고 범주에 대 한 속성을 변경할 수 있습니다. 설정 파일의 속성 범주를 저장 한 후 속성 값을 저장 하는 방법을 보려면 파일을 검사 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하십시오.  
  
## 설정 범주 만들기  
 이 섹션에 저장 하 고 범주 설정의 값을 복원할 사용자 지정 설정 지점을 사용 합니다.  
  
#### 설정 범주를 만들려면  
  
1.  완료 된 [옵션 페이지 만들기](../extensibility/creating-an-options-page.md)합니다.  
  
2.  VSPackage.resx 파일을 열고 이러한 세 개의 문자열 리소스를 추가 합니다.  
  
    |이름|값|  
    |--------|-------|  
    |106|내 범주|  
    |107|내 설정|  
    |108|OptionInteger 및 OptionFloat|  
  
     그러면 해당 이름을 "My Category" 범주는 개체 "내 설정" 및 "OptionInteger 및 OptionFloat" 범주 설명 리소스가 만들어집니다.  
  
    > [!NOTE]
    >  이 세 가지 범주 이름만 설정 가져오기 및 내보내기 마법사에 나타나지 않습니다.  
  
3.  MyToolsOptionsPackage.cs, 추가 `float` 라는 속성이 `OptionFloat` 에 `OptionPageGrid` 클래스를 다음 예와에서 같이 합니다.  
  
    ```c#  
    public class OptionPageGrid : DialogPage  
    {  
        private int optionInt = 256;  
        private float optionFloat = 3.14F;  
  
        [Category("My Options")]  
        [DisplayName("My Integer option")]  
        [Description("My integer option")]  
        public int OptionInteger  
        {  
            get { return optionInt; }  
            set { optionInt = value; }  
        }  
        [Category("My Options")]  
        [DisplayName("My Float option")]  
        [Description("My float option")]  
        public float OptionFloat  
        {  
            get { return optionFloat; }  
            set { optionFloat = value; }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  `OptionPageGrid` 이제 "My Category" 라는 범주는 두 개의 속성으로 구성 됩니다 `OptionInteger` 및 `OptionFloat`합니다.  
  
4.  추가 <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> 에 `MyToolsOptionsPackage` 클래스 및 CategoryName "My Category"를 지정 하 고, 개체 이름 "My Settings"를 지정 하 고 isToolsOptionPage true로 설정 합니다. 앞에서 만든 Id를 사용 하는 해당 문자열 리소스를 categoryResourceID, objectNameResourceID, 및 DescriptionResourceID를 설정 합니다.  
  
    ```c#  
    [ProvideProfileAttribute(typeof(OptionPageGrid),   
        "My Category", "My Settings", 106, 107, isToolsOptionPage:true, DescriptionResourceID = 108)]  
    ```  
  
5.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스에서 표시 되어야 하는 **그리드 페이지 내** 정수 및 부동 소수점 값 모두 설정 되었습니다.  
  
## 설정 파일 검사  
 이 섹션에서는 속성 범주 값 설정 파일을 내보냅니다. 파일을 검토 하 고 다시 속성 범주에는 값을 가져옵니다.  
  
1.  F5 키를 눌러 디버그 모드에서 프로젝트를 시작 합니다. 실험적 인스턴스에서 시작 됩니다.  
  
2.  열기는 **도구 \/ 옵션** 대화 합니다.  
  
3.  왼쪽 창의 트리 뷰에서 확장 **My Category** 클릭 하 고 **그리드 페이지 내**합니다.  
  
4.  값을 변경 **OptionFloat** 3.1416 하 고 **OptionInteger** 12.**확인**을 클릭합니다.  
  
5.  **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  
  
     **설정 가져오기 및 내보내기** 마법사가 나타납니다.  
  
6.  확인 **선택한 환경 설정 내보내기** 을 선택한 다음 클릭 **다음**합니다.  
  
     **내보낼 설정 선택** 페이지가 나타납니다.  
  
7.  클릭 **내 설정**합니다.  
  
     **설명** 변경 **OptionInteger 및 OptionFloat**합니다.  
  
8.  다음 사항을 확인 **내 설정** 을 선택한 다음 클릭 하는 유일한 범주 **다음**합니다.  
  
     **설정 파일 이름** 페이지가 나타납니다.  
  
9. 새 설정 파일의 이름을 `MySettings.vssettings` 적절 한 디렉터리에 저장 합니다.**마침**을 클릭합니다.  
  
     **내보내기 완료** 페이지를 보고 하 여 설정을 내보냈습니다.  
  
10. 에 **파일** 메뉴에서 **열려**, 를 클릭 하 고 **파일**합니다. 찾을 `MySettings.vssettings` 엽니다.  
  
     \(사용자 Guid 다릅니다\) 파일의 다음 섹션에서 내보낸 속성 범주를 찾을 수 있습니다.  
  
    ```  
    <Category name="My Category_My Settings"   
          Category="{4802bc3e-3d9d-4591-8201-23d1a05216a6}"   
          Package="{6bb6942e-014c-489e-a612-a935680f703d}"   
          RegisteredName="My Category_My Settings">  
          PackageName="MyToolsOptionsPackage">  
       <PropertyValue name="OptionFloat">3.1416</PropertyValue>   
       <PropertyValue name="OptionInteger">12</PropertyValue>   
    </Category>  
    ```  
  
     범주 이름 개체 이름 뒤에 밑줄이 추가 하 여 전체 범주 이름이 형성 되도록 확인 합니다. OptionFloat 및 OptionInteger 내보낸된 값과 함께 범주에 나타납니다.  
  
11. 설정 파일을 변경 하지 않고 닫습니다.  
  
12. 에 **도구** 메뉴에서 클릭 **옵션**, 확장 **My Category**, 클릭 **그리드 페이지 내** 다음의 값을 변경 하 고 **OptionFloat** 1.0 및 **OptionInteger** 1로 합니다.**확인**을 클릭합니다.  
  
13. 에 **도구** 메뉴 클릭 **설정 가져오기 및 내보내기**, 선택, **선택한 환경 설정 가져오기**, 클릭 하 고 **다음**합니다.  
  
     **현재 설정 저장** 페이지가 나타납니다.  
  
14. 선택 **아니요, 새 설정을 가져와** 클릭 하 고 **다음**합니다.  
  
     **가져올 설정 모음 선택** 페이지가 나타납니다.  
  
15. 선택의 `MySettings.vssettings` 파일에 **내 설정** 트리 뷰의 노드에 있습니다. 트리 뷰에서 파일이 없으면 클릭 **찾아보기** 찾을 합니다.**다음**을 클릭합니다.  
  
     **가져올 설정을 선택** 대화 상자가 나타납니다.  
  
16. 다음 사항을 확인 **내 설정** 을 선택한 다음 클릭 **마침**합니다. 경우는 **가져오기 완료** 클릭 페이지가 표시 되 면 **닫기**합니다.  
  
17. 에 **도구** 메뉴에서 클릭 **옵션**, 확장 **My Category**, 클릭 **그리드 페이지 내** 속성 범주 값이 복원 되었는지 확인 하 고 있습니다.