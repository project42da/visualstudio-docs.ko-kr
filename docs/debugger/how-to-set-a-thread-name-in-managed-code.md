---
title: "방법: 관리 코드에 스레드 이름 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버깅[Visual Studio], 스레드"
  - "스레드 이름"
  - "Thread.Name 속성"
  - "스레딩[Visual Studio], 이름"
ms.assetid: c0c4d74a-0314-4b71-81c9-b0b019347ab8
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 관리 코드에 스레드 이름 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

스레드 명명 기능은 Visual Studio의 모든 버전에서 사용할 수 있습니다.  이 기능은 **스레드** 창에서 스레드를 추적할 때 유용합니다.  Visual Studio Express 버전에서는 **스레드** 창을 사용할 수 없으므로 Express 버전에서는 스레드 명명이 유용하지 않습니다.  
  
 관리 코드에 스레드 이름을 설정하려면 <xref:System.Threading.Thread.Name%2A> 속성을 사용합니다.  
  
## 예제  
  
```  
Public Class Needle  
    ' This method will be called when the thread is started.  
    Sub Baz()  
        Console.WriteLine("Needle Baz is running on another thread")  
    End Sub  
End Class  
  
Sub Main()  
    Console.WriteLine("Thread Simple Sample")  
    Dim oNeedle As New Needle()  
   ' Create a Thread object.   
    Dim oThread As New System.Threading.Thread(AddressOf oNeedle.Baz)  
    ' Set the Thread name to "MainThread".  
    oThread.Name = "MainThread"  
    ' Starting the thread invokes the ThreadStart delegate  
    oThread.Start()  
End Sub  
```  
  
## 참고 항목  
 [다중 스레드 응용 프로그램 디버깅](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [방법: 네이티브 코드에 스레드 이름 설정](../debugger/how-to-set-a-thread-name-in-native-code.md)