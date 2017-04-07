---
title: "64 비트 디버거 COM 클래스 등록 마이그레이션 | Microsoft 문서"
ms.custom: 
ms.date: 11/10/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
caps.latest.revision: 1
author: gregg-miskelly
ms.author: greggm
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
ms.sourcegitcommit: 8163a0e1230712734936b7548bef1753ee0c1d2a
ms.openlocfilehash: 19ce2d4cc1ff92240529f35f42845778ded49fdf
ms.lasthandoff: 03/07/2017

---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>64 비트 디버거 COM 클래스 등록 마이그레이션

(을 사용 하 여 regasm regsvr32, 레지스트리를 직접 작성) HKEY_CLASSES_ROOT에서 COM 클래스를 등록 하 고 msvsmon.exe (원격 디버거)에 로드 하는 디버거 확장에 대 한 HKEY_CLASSES_ROOT로 쓸 필요 없이이 등록 msvsmon 제공할 수 있도록 되었습니다. 레거시.NET 디버거 식 계산기 또는 msvsmon.exe 프로세스에서 로드 하도록 구성 된 디버그 엔진에 영향을 줍니다.

## <a name="msvsmon-comclass-def"></a>msvsmon-comclass-def

이 기법을 사용 하려면 msvsmon (InstallDir:\Common7\IDE\Remote Debugger\x64) 옆에 있는 *.msvsmon-comclass-def.json 파일을 추가 합니다.

다음은 관리 되는 하나를 등록 하는 예제 msvsmon-comclass-def 파일 및 하나의 기본 클래스입니다.

파일 이름: MyCompany.MyExample.msvsmon comclass def.json

```json
{
  "managedCOMClasses": [
    {
      "clsid": "{C9F48B25-36ED-4B22-8210-98BC5BE4D1E7}",
      "assemblyName": "MyCompany.MyAssembly",
      "className": "MyCompany.MyNamespace.MyClass"
    }
  ],
  "nativeCOMClasses": [
    {
      "clsid": "{42A476E9-8FA7-44D5-ADFE-216AD371EEC9}",
      "dllPath": "MyExample.dll"
    }
  ]
}
```

