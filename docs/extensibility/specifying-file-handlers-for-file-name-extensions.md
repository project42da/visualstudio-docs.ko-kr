---
title: 파일 이름 확장명에 대 한 파일 처리기 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- file extensions, specifying file handlers
ms.assetid: e3de4730-a95c-465a-b3b2-92ca85364ad7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0d0086f8badb32431c85f16e1f74fe8f186c9b2e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="specifying-file-handlers-for-file-name-extensions"></a>파일 이름 확장명에 대 한 파일 처리기 지정
다양 한 방법으로 특정 파일 확장명을 가진 파일을 처리 하는 응용 프로그램을 확인할 수 있습니다. OpenWithList 및 Openwithprogid 동사에는 파일 확장명에 대 한 레지스트리 항목에서 파일 처리기를 지정 하려면 두 가지 있습니다.  
  
## <a name="openwithlist-verb"></a>OpenWithList 동사  
 Windows 탐색기에서 파일을 마우스 오른쪽 단추로 클릭할 때 표시 된 **열려** 명령입니다. 둘 이상의 제품 관련 확장 된 경우 참조는 **프로그램** 하위 메뉴입니다.  
  
 여러 응용 프로그램이 확장 HKEY_CLASSES_ROOT에 파일 확장명에 대 한 OpenWithList 키를 설정 하 여 열을 등록할 수 있습니다. 파일 확장명에 대 한이 키 아래 나열 된 응용 프로그램 아래에 표시 된 **권장 프로그램** 에서 **연결 프로그램** 대화 상자. 다음 예제에서는.vcproj 파일 확장명을 열려면 등록 된 응용 프로그램을 보여 줍니다.  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithList\  
         devenv.exe  
```  
  
> [!NOTE]
>  HKEY_CLASSES_ROOT\Applications 아래의 목록에서 키는 응용 프로그램을 지정 합니다.  
  
 OpenWithList 키를 추가 하 여 다른 응용 프로그램에서는 확장의 소유권을 하는 경우에 응용 프로그램 파일 확장명을 지원함을 선언 합니다. 이 응용 프로그램 또는 다른 응용 프로그램의 이후 버전을 수 있습니다.  
  
## <a name="openwithprogids"></a>Openwithprogid  
 프로그래밍 방식 식별자 (Progid)는 친숙 한 버전의 응용 프로그램 또는 COM 개체의 버전을 식별 하는 Classid입니다. 모든 공동으로 만들 수 있는 개체에는 고유한 ProgID 있어야 합니다. VisualStudio.DTE.10.0 시작 되는 동안 Visual Studio.NET 2003 VisualStudio.DTE.7.1 시작 하는 예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 프로젝트 형식 또는 프로젝트 항목 형식의 소유자로 파일 확장명에 대 한 버전별 ProgID 만들어야 합니다. 둘 이상의 ProgID 동일한 응용 프로그램을 시작할 수 있다는 점에서이 Progid 중복 될 수 있습니다. 자세한 내용은 참조 [파일 이름 확장명에 대 한 등록 동사](../extensibility/registering-verbs-for-file-name-extensions.md)합니다.  
  
 버전이 지정 된 Progid 파일에 대 한 명명 규칙을 사용 하 여 다른 공급 업체의 등록을 중복을 피하기 위해:  
  
|파일 확장명|버전이 지정 된 ProgID|  
|--------------------|----------------------|  
|.extension|제품 이름입니다. extension.versionMajor.versionMinor|  
  
 특정 파일 확장명 값으로는 HKEY_CLASSES_ROOT에 버전이 지정 된 Progid를 추가 하 여 열 수 있는 응용 프로그램을 등록할 수 있습니다\\*\<확장 >*\OpenWithProgids 키입니다. 이 레지스트리 키에는 파일 확장명과 연결 된 대체 Progid의 목록이 포함 되어 있습니다. 나열 된 Progid와 관련 된 응용 프로그램에 표시 된 **프로그램 * * * 제품 이름* 하위 메뉴입니다. 동일한 응용 프로그램 모두에 지정 된 경우는 `OpenWithList` 및 `OpenWithProgids` 키, 운영 체제는 중복을 병합 합니다.  
  
> [!NOTE]
>  `OpenWithProgids` 키만 Windows XP에서 지원 됩니다. 다른 운영 체제의이 키를 무시 하기 때문에 사용 하지 마십시오 것만 등록으로 파일 처리기에 대 한. 이 키를 사용 하 여 Windows XP에서 더 나은 사용자 환경을 제공 합니다.  
  
 REG_NONE 형식의 값으로 원하는 Progid를 추가 합니다. 다음 코드는 파일 확장명에 대 한 Progid 등록의 예를 제공 합니다. (. *ext*).  
  
```  
HKEY_CLASSES_ROOT\  
   .ext\  
      (default)="MyProduct.ext.14.0"  
      OpenWithProgids  
         progid        REG_NONE (zero-length binary value)  
         otherprogid   REG_NONE (zero-length binary value)  
```  
  
 파일 확장명에 대 한 기본값은 기본 파일 처리기가 지정 된 ProgID입니다. 이전 버전의 함께 제공 되는 파일 확장명에 대 한 ProgID를 수정 하는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 또는 다른 응용 프로그램 키를 사용할 수 있는 다음 등록 해야 합니다는 `OpenWithProgids` 와 함께 목록에 새 ProgID를 지정 하 고 파일 확장명에 대 한 키 지 원하는 이전 Progid입니다. 예를 들어:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithProgids  
         vcprojfile              //old progid  
         VisualStudio.vcproj.12.0 //old progid  
         VisualStudio.vcproj.14.0 //new progid  
```  
  
 이전 ProgID에 연결 된 동사 경우 이러한 동사에도 나타납니다 **프로그램** *제품 이름* 의 바로 가기 메뉴.  
  
## <a name="see-also"></a>참고 항목  
 [파일 이름 확장명에 대 한](../extensibility/about-file-name-extensions.md)   
 [파일 이름 확장명에 대한 동사 등록](../extensibility/registering-verbs-for-file-name-extensions.md)