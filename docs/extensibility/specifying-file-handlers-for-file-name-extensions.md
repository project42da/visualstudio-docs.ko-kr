---
title: "파일 이름 확장명에 대 한 파일 처리기 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "파일 확장명을 파일 처리기를 지정 합니다."
ms.assetid: e3de4730-a95c-465a-b3b2-92ca85364ad7
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# 파일 이름 확장명에 대 한 파일 처리기 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다양 한 방법으로 특정 파일 확장명을 가진 파일을 처리 하는 응용 프로그램을 확인할 수 있습니다. OpenWithList 및 Openwithprogid 동사에는 파일 확장명에 대 한 레지스트리 항목에서 파일 처리기를 지정 하려면 두 가지 있습니다.  
  
## OpenWithList 동사  
 Windows 탐색기에서 파일을 마우스 오른쪽 단추로 표시는 **열려** 명령입니다. 둘 이상의 제품을는 확장명과 연결 하는 경우 참조는 **Open With** 하위 메뉴입니다.  
  
 다른 응용 프로그램을 HKEY\_CLASSES\_ROOT에서 파일 확장명에 대 한 OpenWithList 키를 설정 하 여 확장을 열지를 등록할 수 있습니다. 파일 확장명에 대 한이 키 아래에 나열 된 응용 프로그램 아래에 표시는 **권장 프로그램** 에서 **Open With** 대화 상자입니다. 다음 예제에서는.vcproj 파일 확장명을 열려면 등록 된 응용 프로그램을 보여 줍니다.  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithList\  
         devenv.exe  
```  
  
> [!NOTE]
>  HKEY\_CLASSES\_ROOT\\Applications 아래의 목록에서 키는 응용 프로그램을 지정 합니다.  
  
 OpenWithList 키를 추가 하 여 다른 응용 프로그램에서는 확장의 소유권을 하는 경우에 응용 프로그램 파일 확장명을 지원함을 선언 합니다. 이후 버전의 응용 프로그램 또는 다른 응용 프로그램 수 있습니다.  
  
## Openwithprogid  
 프로그래밍 방식 식별자 \(Progid\)는 응용 프로그램 또는 COM 개체의 버전을 식별 하는 classid의 친숙 한 버전이 있습니다. 모든 공동으로 만들 수 있는 개체는 고유한 ProgID가 있어야 합니다. VisualStudio.DTE.10.0 시작 되는 동안 VisualStudio.DTE.7.1 Visual Studio.NET 2003을 시작 하는 예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 프로젝트 형식 또는 프로젝트 항목 형식 소유자로 파일 확장명에 대 한 버전별 ProgID를 만들어야 합니다. 둘 이상의 ProgID 동일한 응용 프로그램을 시작할 수 있다는 점에서 이러한 Progid 중복 될 수 있습니다. 자세한 내용은 [파일 이름 확장명에 대 한 동사를 등록 하는 중](../extensibility/registering-verbs-for-file-name-extensions.md)을 참조하세요.  
  
 다른 공급 업체의 등록을 통해 중복을 피하기 위해 버전이 지정 된 Progid 파일에 대 한 다음 명명 규칙을 사용 합니다.  
  
|파일 확장명|버전이 지정 된 ProgID|  
|------------|---------------------|  
|.extension|제품 이름입니다. extension.versionMajor.versionMinor|  
  
 값으로는 중이지에 버전이 지정 된 Progid를 추가 하 여 특정 파일 확장명을 열 수 있는 응용 프로그램을 등록할 수 있습니다*\< 확장 \>*\\OpenWithProgids 키입니다. 이 레지스트리 키에는 파일 확장명과 연결 된 대체 Progid의 목록이 포함 되어 있습니다. 나열 된 Progid와 관련 된 응용 프로그램에 표시 된 **Open With***제품 이름* 하위 메뉴입니다. 동일한 응용 프로그램 모두에 지정 된 경우는 `OpenWithList` 및 `OpenWithProgids` 키, 운영 체제는 중복을 병합 합니다.  
  
> [!NOTE]
>  `OpenWithProgids` 키만 Windows XP에서 지원 됩니다. 다른 운영 체제에서이 키를 무시 하기 때문에 사용 하지 마십시오 것만 등록으로 파일 처리기에 대 한. 이 키를 사용 하 여 Windows XP에서 더 나은 사용자 환경을 제공 합니다.  
  
 REG\_NONE 형식의 값으로 원하는 Progid를 추가 합니다. 다음 코드에서는 파일 확장명에 대 한 Progid를 등록 하는 예 \(.*ext*\).  
  
```  
HKEY_CLASSES_ROOT\  
   .ext\  
      (default)="MyProduct.ext.14.0"  
      OpenWithProgids  
         progid        REG_NONE (zero-length binary value)  
         otherprogid   REG_NONE (zero-length binary value)  
```  
  
 파일 확장명에 대 한 기본값은 기본 파일 처리기로 지정 된 ProgID입니다. 이전 버전과 함께 제공 된 파일 확장명에 대 한 ProgID를 수정 하는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 하거나 다른 응용 프로그램을 통해 수행할 수 있는 다음 등록 해야는 `OpenWithProgids` 파일 확장명에 대 한 키를 지 원하는 이전 Progid와 함께 목록에 새 ProgID를 지정 합니다. 예:  
  
```  
HKEY_CLASSES_ROOT\  
   .vcproj\  
      (default)="VisualStudio.vcproj.14.0"  
      OpenWithProgids  
         vcprojfile              //old progid  
         VisualStudio.vcproj.12.0 //old progid  
         VisualStudio.vcproj.14.0 //new progid  
```  
  
 이전 ProgID에 연결 된 동사 경우 이러한 동사에도 나타납니다 **Open With** *제품 이름* 바로 가기 메뉴에서입니다.  
  
## 참고 항목  
 [파일 이름 확장명에 대 한](../extensibility/about-file-name-extensions.md)   
 [파일 이름 확장명에 대 한 동사를 등록 하는 중](../extensibility/registering-verbs-for-file-name-extensions.md)