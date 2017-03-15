---
title: "Vspackage에서 리소스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed VSPackages, resources in
- resources, managed VSPackages
- VSPackages, managed resources
ms.assetid: cc8c17a6-b190-4856-b001-0c1104f104b2
caps.latest.revision: 23
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 184642501b9452566a15e1aba30312e17500f7bb
ms.lasthandoff: 02/22/2017

---
# <a name="resources-in-vspackages"></a>Vspackage의 리소스
자체 관리 되는 VSPackage 또는 네이티브 위성 UI Dll에 관리 되는 위성 Dll에서에서 지역화 된 리소스를 포함할 수 있습니다.  
  
 Vspackage에서 일부 리소스를 포함할 수 없습니다. 다음 관리 되는 형식은 포함 될 수 있습니다.  
  
-   문자열  
  
-   패키지 로드 키 (또한 문자열)  
  
-   도구 창 아이콘  
  
-   컴파일된 명령 테이블 출력 (CTO) 파일  
  
-   CTO 비트맵  
  
-   명령줄 도움말  
  
-   대화 상자 데이터에 대 한  
  
 리소스는 관리 되는 패키지의 리소스 id 선택 예외는 CTO 파일을 CTMENU 이름을 지정 해야 합니다. CTO 파일 리소스 테이블에 표시 되어야는 `byte[]`합니다. 다른 모든 리소스 항목 유형으로 식별 됩니다.  
  
 사용할 수는 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>특성을 나타내는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 관리 되는 리소스를 사용할 수 있는지.</xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>  
  
 [!code-cs[#1 VSSDKResources](../../extensibility/internals/codesnippet/CSharp/resources-in-vspackages_1.cs)]
 [!code-vb[VSSDKResources&#1;](../../extensibility/internals/codesnippet/VisualBasic/resources-in-vspackages_1.vb)]  
  
 설정 <xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute>이 방식으로 나타내는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 검색 되는 경우 리소스에 대 한 예를 들어 <xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A>.</xref:Microsoft.VisualStudio.Shell.Interop.IVsShell.LoadPackageString%2A> 를 사용 하 여 관리 되지 않는 위성 Dll을 무시 해야</xref:Microsoft.VisualStudio.Shell.PackageRegistrationAttribute> 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 동일한 리소스 id는 두 개 이상의 리소스를 발견 찾은 첫 번째 리소스를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 도구 창 아이콘의 관리 되는 표현입니다.  
  
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
  
 다음 예제에서는 CTMENU 이름을 지정 하 여 CTO 바이트 배열에 포함 하는 방법을 보여 줍니다.  
  
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
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]가능 하면 Vspackage의 지연 로드 합니다. VSPackage에서 CTO 파일을 포함 합니다. 따라서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 병합된 명령 테이블을 작성 하는 경우 설치 하는 동안 메모리에 이러한 모든 Vspackage를 로드 해야 합니다. VSPackage에서 코드를 실행 하지 않고 메타 데이터를 검사 하 여 VSPackage에서 리소스를 추출할 수 있습니다. 성능 저하는 미미 하므로이 이번에는 VSPackage 초기화 되지 않았습니다.  
  
 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치가 끝난 후 VSPackage에서 리소스를 요청, 해당 패키지 이므로 이미 로드 되 고 초기화 가능성이 성능 저하는 미미 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리 되는 VSPackages](../../misc/managed-vspackages.md)   
 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)   
 [MFC 응용 프로그램의 지역화 된 리소스: 위성 Dll](http://msdn.microsoft.com/Library/3a1100ae-a9c8-47b5-adbd-cbedef5992ef)   
 [관리되는 VSPackage](../../misc/managed-vspackages.md)
