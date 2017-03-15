---
title: "함수 포인터인 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: bb576b9c-4cde-406a-9069-e8500a7da9f7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 함수 포인터인 연산자
이 콘텐츠는 제거되었습니다. 자세한 내용은 [함수 호출 연산자 오버로드](/visual-cpp/cpp/function-call-cpp)를 참조하세요.  
  
```  
// operator_that_is_pointer_to_function.cpp  
// function style call on object will invoke user-defined conversion   
// if there is one. See secion 13.3.1.1.2   
typedef void(*ptf)();  
void func()  
{  
}  
struct S  
{  
   operator ptf()  
   {  
      return func;  
   }  
};  
  
int main()  
{  
   S s;  
   s();//operates as s.operator ptf()()  
}  
```  
  
## 참고 항목  
 [향상된 Visual C\+\+ .NET 2003 컴파일러 규칙](../misc/visual-cpp-dotnet-2003-enhanced-compiler-conformance.md)