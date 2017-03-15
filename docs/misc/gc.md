---
title: "__gc | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__gc"
  - "__gc_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__gc 형식"
  - "관리 되는 클래스 [c + +]"
  - "관리되는 클래스"
ms.assetid: 63b1e7ab-d1c8-4582-aa89-21bfddf694a9
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __gc
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [Classes and Structs](/visual-cpp/windows/classes-and-structs-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 \_\_gc 형식을 선언합니다.  
  
## 구문  
  
```  
  
__gc  
array-specifier  
__gc   
class-specifier  
__gc   
struct-specifier  
__gc  
interface-specifier  
__gc  
pointer-specifier  
__gc new  
  
```  
  
## 설명  
 \_\_gc 형식은 상호 운용성 및 가비지 수집과 같은 기능을 제공하여 .NET Framework 프로그래밍을 간소화하는 C\+\+ 언어 확장입니다.  
  
> [!NOTE]
>  멤버 함수가 순수하게 가상이 아닌 한 추상 \_\_gc 클래스의 모든 멤버 함수를 정의해야 합니다.  
  
 Managed Extensions for C\+\+에서 C\# 클래스와 C\# 구조체에 해당하는 요소는 다음과 같습니다.  
  
|Managed Extensions for C\+\+|C\#|추가 정보|  
|----------------------------------|---------|-----------|  
|\_\_gc 구조체 또는 \_\_gc 클래스|클래스|[class](/dotnet/csharp/language-reference/keywords/class) 키워드|  
|\_\_value 구조체 또는 \_\_value 클래스|struct|[struct](/dotnet/csharp/language-reference/keywords/struct) 키워드|  
  
## 예제  
 다음 예제에서 관리되는 클래스\(`X`\)는 관리되는 포인터를 통해 조작되는 public 데이터 멤버를 사용하여 선언됩니다.  
  
```  
// keyword__gc.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class X {  
public:  
   int i;  
   int ReturnInt() { return 5; }  
};  
  
int main() {  
   // X is a __gc class, so px is a __gc pointer  
   X* px;  
   px = new X;   // creates a managed object of type X  
   Console::WriteLine(px->i);  
  
   px->i = 4;   // modifies X::i through px  
   Console::WriteLine(px->i);  
  
   int n = px->ReturnInt();   // calls X::ReturnInt through px  
   Console::WriteLine(n);  
}  
```  
  
## 출력  
  
```  
0  
4  
5  
```