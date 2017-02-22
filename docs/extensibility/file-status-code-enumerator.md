---
title: "파일 상태 코드 열거자 | Microsoft Docs"
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
  - "명명 된 상수, SccStatus 열거자"
  - "소스 제어 플러그 인, 파일 상태 열거"
  - "SccStatus 열거자"
  - "파일 상태 코드 열거자"
ms.assetid: 5c37876b-c83c-4ca1-837b-57cd465a879a
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 파일 상태 코드 열거자
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`SccStatus` 소스 제어 시스템에서 파일의 상태를 지정 하는 명명 된 상수 값을 포함 하는 열거자입니다. 이 열거형을 사용 하 여는 [SccQueryInfo](../extensibility/sccqueryinfo-function.md) 및 `POPLISTFUNC` 콜백 함수 \(참조 [POPLISTFUNC](../extensibility/poplistfunc.md) 대 한 자세한 내용은\).  
  
## 구문  
  
```  
enum SccStatus {  
   SCC_STATUS_INVALID          = -1L,  
   SCC_STATUS_NOTCONTROLLED    = 0x0000L,  
   SCC_STATUS_CONTROLLED       = 0x0001L,  
   SCC_STATUS_CHECKEDOUT       = 0x0002L,  
   SCC_STATUS_OUTOTHER         = 0x0004L,  
   SCC_STATUS_OUTEXCLUSIVE     = 0x0008L,  
   SCC_STATUS_OUTMULTIPLE      = 0x0010L,  
   SCC_STATUS_OUTOFDATE        = 0x0020L,  
   SCC_STATUS_DELETED          = 0x0040L,  
   SCC_STATUS_LOCKED           = 0x0080L,  
   SCC_STATUS_MERGED           = 0x0100L,  
   SCC_STATUS_SHARED           = 0x0200L,  
   SCC_STATUS_PINNED           = 0x0400L,  
   SCC_STATUS_MODIFIED         = 0x0800L,  
   SCC_STATUS_OUTBYUSER        = 0x1000L  
   SCC_STATUS_NOMERGE          = 0x2000L  
   SCC_STATUS_RESERVED_1       = 0x4000L  
   SCC_STATUS_RESERVED_2       = 0x8000L  
};  
```  
  
## 멤버  
 SCC\_STATUS\_INVALID  
 상태를 가져올 수 없습니다. 에 의존 하지 않습니다.  
  
 SCC\_STATUS\_NOTCONTROLLED  
 파일은 소스 제어에서 아닙니다.  
  
 SCC\_STATUS\_CONTROLLED  
 소스 제어에서 파일이 있습니다.  
  
 SCC\_STATUS\_CHECKEDOUT  
 로컬 디스크에 현재 사용자가 체크 아웃 합니다.  
  
 SCC\_STATUS\_OUTOTHER  
 파일이 다른 사용자가 체크 아웃 됩니다.  
  
 SCC\_STATUS\_OUTEXCLUSIVE  
 파일이는 배타적으로 체크 아웃 됩니다.  
  
 SCC\_STATUS\_OUTMULTIPLE  
 파일은 둘 이상의 사용자가 체크 아웃 됩니다.  
  
 SCC\_STATUS\_OUTOFDATE  
 파일이 최신 아닙니다.  
  
 SCC\_STATUS\_DELETED  
 프로젝트에서 파일 삭제 되었습니다.  
  
 SCC\_STATUS\_LOCKED  
 파일이 잠겨 있습니다. 더 많은 버전 허용.  
  
 SCC\_STATUS\_MERGED  
 파일 병합 되었지만 아직 고정\/확인할 수 있습니다.  
  
 SCC\_STATUS\_SHARED  
 파일은 프로젝트 간에 공유 됩니다.  
  
 SCC\_STATUS\_PINNED  
 파일은 특정 버전에 공유 됩니다.  
  
 SCC\_STATUS\_MODIFIED  
 파일 수정\/분할\/위반 했습니다.  
  
 SCC\_STATUS\_OUTBYUSER  
 파일이 현재 사용자가 체크 아웃 됩니다.  
  
 SCC\_STATUS\_NOMERGE  
 파일과으로 병합 되지 않고 수 GET 하기 전에 저장 되지 있습니다.  
  
 SCC\_STATUS\_RESERVED\_1  
 내부용으로 예약됩니다.  
  
 SCC\_STATUS\_RESERVED\_2  
 내부용으로 예약됩니다.  
  
## 참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [SccQueryInfo](../extensibility/sccqueryinfo-function.md)   
 [POPLISTFUNC](../extensibility/poplistfunc.md)