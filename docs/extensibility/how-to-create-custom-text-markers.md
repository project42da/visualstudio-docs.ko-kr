---
title: '방법: 사용자 지정 텍스트 표식 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - custom text markers
ms.assetid: 6e32ed81-c604-4a32-9012-8db3bec7c846
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f5c44a507cc291b203fc9ba330b248a854f61b81
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-custom-text-markers"></a>방법: 사용자 지정 텍스트 표식 만들기
강조 하거나 코드를 구성 하는 사용자 지정 텍스트 표식을 만들려는 경우에 다음 단계를 수행 해야 합니다.  
  
-   다른 도구에 액세스할 수 있도록 새 텍스트 표식 등록  
  
-   텍스트 표식의 구성과 기본 구현을 제공합니다  
  
-   다른 프로세스에서 사용할 수 있는 서비스 만들기 텍스트 표식 사용  
  
 텍스트 표식 코드 영역에 적용 하는 방법에 대 한 세부 정보를 참조 하십시오. [하는 방법: 사용 하 여 텍스트 표식](../extensibility/how-to-use-text-markers.md)합니다.  
  
### <a name="to-register-a-custom-marker"></a>사용자 지정 마커를 등록 하려면  
  
1.  다음과 같이 레지스트리 항목을 만듭니다.  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<버전 >*\Text Editor\External 표식\\*\<MarkerGUID >*  
  
     *\<MarkerGUID >*는 `GUID` 추가 중인 마커를 식별 하는 데 사용  
  
     *\<버전 >* 의 버전이 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], 예를 들어 8.0  
  
     *\<PackageGUID >* 자동화 개체를 구현 하는 VSPackage의 GUID입니다.  
  
    > [!NOTE]
    >  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio의 루트 경로\\*\<버전 >* 자세한 내용은 Visual Studio shell 초기화 될 때 대체 루트로 재정의할 수 있습니다 [명령줄 스위치](../extensibility/command-line-switches-visual-studio-sdk.md)합니다.  
  
2.  HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio에서 4 개의 값을 만들\\*\<버전 >*\Text Editor\External 표식\\*\<MarkerGUID >*  
  
    -   (기본값)  
  
    -   서비스  
  
    -   DisplayName  
  
    -   패키지  
  
    -   `Default` REG_SZ 형식의 선택적 항목이입니다. 항목의 값에 몇 가지 유용한 식별 정보, 예를 들어 "사용자 지정 텍스트 표식"를 포함 하는 문자열은으로 설정 하면 합니다.  
  
    -   `Service` 사용자 지정 텍스트 표식 proffering에서 제공 하는 서비스의 GUID 문자열이 포함 된 REG_SZ 유형의 항목은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider>합니다. 형식은 {XXXXXX XXXX XXXX XXXX XXXXXXXXX}입니다.  
  
    -   `DisplayName` 사용자 지정 텍스트 표식 이름의 리소스 ID 포함 된 REG_SZ 유형의 항목입니다. 형식은 #YYYY입니다.  
  
    -   `Package` 항목의 종류 REG_SZ를 포함 하는 `GUID` 서비스 아래 나열 된 서비스를 제공 하는 VSPackage의 합니다. 형식은 {XXXXXX XXXX XXXX XXXX XXXXXXXXX}입니다.  
  
### <a name="to-create-a-custom-text-marker"></a>사용자 지정 텍스트 마커를 만들려면  
  
1.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsPackageDefinedTextMarkerType> 인터페이스를 구현합니다.  
  
     이 인터페이스의 구현 동작과 사용자 지정 표식 형식의 모양을 정의합니다.  
  
     이 인터페이스는 될 때 호출 됩니다.  
  
    1.  사용자가 처음으로 IDE를 시작 합니다.  
  
    2.  사용자가 선택는 **기본값 재설정** 단추는 **글꼴 및 색** 속성 페이지에는 **환경** 의 왼쪽된 창에 있는 폴더는  **옵션** 대화 상자에서 가져온는 **도구** IDE의 메뉴.  
  
2.  구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider.GetTextMarkerType%2A> 메서드를 지정 하는 `IVsPackageDefinedTextMarkerType` 구현 해야 기반으로 반환 될 표식 유형 메서드 호출에 지정 된 GUID입니다.  
  
     환경은 사용자 지정 표식 유형을 작성 되 고 사용자 지정 표식 유형을 식별 하는 GUID를 지정 합니다.이 메서드는 첫 번째 시간을 호출 합니다.  
  
### <a name="to-proffer-your-marker-type-as-a-service"></a>표식 유형을 서비스로 proffer를  
  
1.  호출 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleComponentManager.QueryService%2A> 방법을 <xref:Microsoft.VisualStudio.Shell.Interop.SProfferService>합니다.  
  
     에 대 한 포인터 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> 반환 됩니다.  
  
2.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.ProfferService%2A> 메서드를 사용자 지정 표식 형식 서비스를 식별 하 고 구현에 대 한 포인터를 제공 하는 GUID를 지정 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 인터페이스입니다. 프로그램 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> 구현은 구현에 대 한 포인터를 반환 해야 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextMarkerTypeProvider> 인터페이스입니다.  
  
     서비스를 식별 하는 고유한 쿠키 반환 됩니다. 이 쿠키를 호출 하 여 사용자 지정 표식 유형 서비스를 해지 하려면 나중에 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService.RevokeService%2A> 의 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> 이 쿠키 값을 지정 하는 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 표식 레거시 API 사용](../extensibility/using-text-markers-with-the-legacy-api.md)   
 [방법: 표준 텍스트 표식을 추가](../extensibility/how-to-add-standard-text-markers.md)   
 [방법: 오류 마커를 구현 합니다.](../extensibility/how-to-implement-error-markers.md)   
 [방법: 텍스트 표식을 사용 하 여](../extensibility/how-to-use-text-markers.md)