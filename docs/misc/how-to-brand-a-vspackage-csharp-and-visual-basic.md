---
title: "방법: VSPackage 브랜딩(C# 및 Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "정보 대화 상자"
  - "VSPackage, 시작 화면"
  - "VSPackage, 브랜딩"
ms.assetid: 705a41c3-63d6-4c1e-9f82-771be9191579
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# 방법: VSPackage 브랜딩(C# 및 Visual Basic)
에 있는  **에 대 한** 대화 상자 및 시작 화면, Vspackages를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct> 인터페이스입니다.  이 다음과 같은 정보를 제공 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]:  
  
-   Name  
  
-   직렬 포트 또는 버전 번호와 같은 ID  
  
-   정보  
  
-   로고 아이콘  
  
 다음 코드는 [VSSDK 샘플](../misc/vssdk-samples.md).  
  
### IVsInstalledProduct 인터페이스를 구현 하려면  
  
1.  추가 <xref:Microsoft.VisualStudio.Shell.InstalledProductRegistrationAttribute> 특성이 있는 Vspackage를 구현 하는 클래스에 있습니다.  이 클래스를 파생 해야 합니다 <xref:Microsoft.VisualStudio.Shell.Package> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct>.  
  
     [!code-cs[VSSDKPackageSplashHelpAboutLoadKey#1](../misc/codesnippet/CSharp/how-to-brand-a-vspackage-csharp-and-visual-basic_1.cs)]
     [!code-vb[VSSDKPackageSplashHelpAboutLoadKey#1](../misc/codesnippet/VisualBasic/how-to-brand-a-vspackage-csharp-and-visual-basic_1.vb)]  
  
     인수를 <xref:Microsoft.VisualStudio.Shell.InstalledProductRegistrationAttribute.UseInterface%2A>의 <xref:Microsoft.VisualStudio.Shell.InstalledProductRegistrationAttribute> 특성을 알 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 사용 하도록 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct> InstalledProducts 레지스트리 키 대신 제품 정보를 얻을 수.  나머지 인수는 제품 이름, 정보, ID, 각각 표시 하는 문자열 리소스를 선택 합니다.  그러나, 첫 번째 인수 이므로 `true`, 나머지 인수는 `null`.  
  
2.  마우스 오른쪽 단추로 클릭 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct>, 가리킨  **인터페이스 구현**, 다음을 클릭 하 고  **인터페이스 구현**.  
  
3.  구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsInstalledProduct> 다음 코드를 사용 하 여.  
  
     [!code-cs[VSSDKPackageSplashHelpAboutLoadKey#2](../misc/codesnippet/CSharp/how-to-brand-a-vspackage-csharp-and-visual-basic_2.cs)]
     [!code-vb[VSSDKPackageSplashHelpAboutLoadKey#2](../misc/codesnippet/VisualBasic/how-to-brand-a-vspackage-csharp-and-visual-basic_2.vb)]  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]있는 VSPackage 브랜딩에 대 한 정보를 얻기 위해 이러한 메서드를 호출 합니다.  GetResourceString 메서드를 사용 하 여이 정보를 지역화 합니다.  
  
    > [!NOTE]
    >  코드 설명은 간단히 하기 위해 삭제 됩니다.  찾을 수 있습니다 [VSSDK 샘플](../misc/vssdk-samples.md).  
  
### 제품 정보를 유지 하는 문자열  
  
1.  VSPackage 함께 연결 된.resx 리소스 파일을 두 번 클릭 합니다.  
  
     리소스 편집기가 열립니다.  
  
2.  찾기 또는 제품 이름, 정보를 추가 하 고 id.  
  
     다음 리소스 문자열에서 되는 [VSSDK 샘플](../misc/vssdk-samples.md).  
  
     @101  
     패키지 시작 화면 및 도움말에 대 한 공식적인 이름 \(C\#\).  
  
     @102  
     이 패키지는 시작 화면 및 도움말에 대 한 텍스트와 이미지를 표시 하는 방법을 보여 줍니다.  
  
     @104  
     8.0  
  
3.  선택 하 고 원하는 대로이 정보를 편집 합니다.  
  
### 제품 아이콘 및 비트맵을 유지 관리 하려면  
  
1.  프로젝트에 비트맵 및 아이콘 리소스는 프로젝트 리소스를 추가 합니다.  
  
     자세한 내용은 [NOT IN BUILD: Adding and Editing Resources \(Visual C\#\)](http://msdn.microsoft.com/ko-kr/95f15d03-bed0-410c-8d1f-dece5199ba1e)를 참조하십시오.  
  
2.  리소스 편집기를 닫고 텍스트 또는 XML 편집기에서.resx 파일을 다시 합니다.  
  
    > [!NOTE]
    >  리소스 편집기에서 리소스 Id 문자열이 아닌 항목을 할당을 지원 하지 않습니다.  
  
3.  찾기 또는 비트맵 및 아이콘 리소스는.resx 파일을 추가 합니다.  다음 리소스에서 있습니다 [VSSDK 샘플](../misc/vssdk-samples.md).  
  
    ```  
    <data name="300" type="System.Resources.ResXFileRef, System.Windows.Forms">  
        <value>GenericPackage.bmp;System.Drawing.Bitmap, System.Drawing,  
            Version=2.0.0.0, Culture=neutral,         PublicKeyToken=b03f5f7f11d50a3a</value>  
    </data>  
    <data name="400" type="System.Resources.ResXFileRef, System.Windows.Forms">  
        <value>GenericPackage.ico;System.Drawing.Icon, System.Drawing,  
            Version=2.0.0.0, Culture=neutral,         PublicKeyToken=b03f5f7f11d50a3a</value>  
    </data>  
    ```  
  
### 정보 대화 상자 및 시작 화면을 테스트할 수  
  
-   Vspackage를 테스트 하기를 참조 하십시오 [방법: 도움말 정보 및 시작 화면 테스트](../misc/how-to-test-the-help-about-and-splash-screens.md).  
  
## 참고 항목  
 [VSPackage 브랜딩](../misc/vspackage-branding.md)