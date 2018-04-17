---
title: Vspackage의 리소스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d252f61a9f634f4bb8435626c41c586bbe5cb839
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="resources-in-vspackages"></a>Vspackage의 리소스
자체 관리 되는 VSPackage 또는 네이티브 위성 UI Dll에 관리 되는 위성 Dll에서에서 지역화 된 리소스를 포함할 수 있습니다.  
  
 일부 리소스는 Vspackage에 포함할 수 없습니다. 다음 관리 되는 형식은 포함 될 수 있습니다.  
  
-   문자열  
  
-   패키지 로드 키 (또한 문자열)  
  
-   도구 창 아이콘  
  
-   컴파일된 명령 테이블 출력 (CTO) 파일  
  
-   CTO 비트맵  
  
-   명령줄 도움말  
  
-   대화 상자 데이터에 대 한  
  
 리소스 관리 되는 패키지의 리소스 id 선택 예외는 CTO 파일을 CTMENU 이름을 지정 해야 합니다. CTO 파일 리소스 테이블에 나타나야 합니다는 `byte[]`합니다. 다른 모든 리소스 항목 유형으로 식별 됩니다.  
  
 사용할 수는 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 특성을 나타내는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 관리 되는 리소스를 사용할 수 있습니다.  
  
 [!code-csharp[VSSDKResources#1](../../extensibility/internals/codesnippet/CSharp/resources-in-vspackages_1.cs)]
 [!code-vb[VSSDKResources#1](../../extensibility/internals/codesnippet/VisualBasic/resources-in-vspackages_1.vb)]  
  
 설정 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 이런이 방식으로 나타내는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 검색 되는 경우 리소스에 대 한 예를 들어를 사용 하 여 관리 되지 않는 위성 Dll을 무시 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A>합니다. 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 동일한 리소스 ID를 포함 하는 둘 이상의 리소스가 발견 찾은 첫 번째 리소스를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 도구 창 아이콘의 관리 되는 표현입니다.  
  
```  
<data name="1001"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyToolWinIcon.bmp;  
     System.Drawing.Bitmap,  
     System.Drawing,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
 다음 예제에서는 CTMENU 이름을 지정 해야 합니다는 CTO 바이트 배열에 포함 하는 방법을 보여 줍니다.  
  
```  
<data name="CTMENU"  
type="System.Resources.ResXFileRef,System.Windows.Forms">  
     <value>  
     MyPackage.cto;  
     System.Byte[],  
     mscorlib,  
     Version=1.0.0.0,  
     Culture=neutral,  
     PublicKeyToken=b03f5f7f11d50a3a  
     </value>  
</data>  
```  
  
## <a name="implementation-notes"></a>구현 참고 사항  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 가능 하면 Vspackage 지연 로드 합니다. 결과는 VSPackage에 CTO 파일을 포함 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 병합된 명령 테이블을 작성 하는 경우 설치 하는 동안 메모리에 이러한 모든 Vspackage를 로드 해야 합니다. VSPackage에서 코드를 실행 하지 않고 메타 데이터를 검사 하 여 VSPackage에서 리소스를 추출할 수 있습니다. 성능 저하는 최소한의 VSPackage,이 이번에 초기화 되지 않았습니다.  
  
 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치 후에 VSPackage에서 리소스는 요청을 해당 패키지는 이미 로드 되어 초기화 가능성이 이므로 성능이 저하 최소화 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)   
 [MFC 응용 프로그램의 지역화된 리소스: 위성 DLL](/cpp/build/localized-resources-in-mfc-applications-satellite-dlls)   
