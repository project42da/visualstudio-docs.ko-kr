---
title: "64 비트 디버거 COM 클래스 등록 마이그레이션 | Microsoft Docs"
ms.custom: 
ms.date: 11/10/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45cfcee6-7a68-4d4f-b3f6-e2d8a0fa066a
caps.latest.revision: "1"
author: gregg-miskelly
ms.author: greggm
manager: ghogen
ms.workload: greggm
ms.openlocfilehash: 737c970555fce8f3cdac118421eddb09f52d7c53
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="migrate-64-bit-debugger-com-class-registration"></a>COM 클래스를 등록 하는 64 비트 디버거 마이그레이션

(사용 하 여 regasm regsvr32, 직접 레지스트리에 쓰는) HKEY_CLASSES_ROOT에 COM 클래스를 등록 하 고 msvsmon.exe (원격 디버거)에 로드 하는 디버거 확장을 위한 이제 수는 필요 없이 msvsmon에이 등록을 제공 합니다. HKEY_CLASSES_ROOT에 쓰려고 합니다. Msvsmon.exe 프로세스에 로드 하도록 구성 된 디버그 엔진 또는 레거시.NET 디버거 식 계산기가 결정 됩니다.

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
