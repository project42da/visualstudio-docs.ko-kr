---
title: Android 디버거 속성(C++) | Microsoft Docs
ms.custom: ''
ms.date: 10/23/2017
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 789f7a1c-38b4-41d0-809b-14f4d96c8116
author: corob
ms.author: mblome
manager: douge
f1_keywords:
- VC.Project.AndroidDebugger.DebuggerType
- VC.Project.AndroidDebugger.AndroidDeviceID
- VC.Project.AndroidDebugger.PackagePath
- VC.Project.AndroidDebugger.LaunchActivity
ms.workload:
- xplat-cplusplus
ms.openlocfilehash: 7d18125c6666a8eb68becd828da36ecdab077507
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="android-debugger-properties"></a>Android 디버거 속성

속성 | 설명 | 선택 항목
--- | ---| ---
디버거 형식 | 디버그할 코드 형식을 지정합니다. | **네이티브 전용**<br>**Java 전용**<br>
디버그 대상 | 디버깅에 사용할 에뮬레이터 또는 장치를 지정합니다. 실행 중인 에뮬레이터가 없으면 'AVD(Android 가상 장치) 관리자'를 사용하여 장치를 시작합니다.
실행할 패키지 | 디버그할 .apk의 위치를 지정합니다. 응용 프로그램을 디버그할 때 특정 패키지(APK)가 시작되도록 지정하려면 이 옵션을 선택합니다.
시작 작업 | 응용 프로그램을 시작하는 데 사용하는 Android 작업은 매니페스트에서 사용하는 것과 일치해야 합니다. [작업]을 눌러 AndroidManifest.xml에서 목록을 검색하고 동적으로 채웁니다.
추가 기호 검색 경로 | 디버그 기호에 대한 추가 검색 경로입니다.
추가 Java 원본 검색 경로 | Java 원본 파일에 대한 추가 검색 경로입니다. (디버거 형식이 Java 전용인 경우에만 적용됩니다.)
