---
title: "__value | Microsoft Docs"
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
  - "__value_cpp"
  - "__value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__value 키워드"
  - "값 형식 선언"
  - "__value 키워드, 구문"
ms.assetid: b14b64f7-5db6-4e92-a144-fcbf67572b49
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __value
> [!NOTE]
>  이 항목은 Managed Extensions for C\+\+ 버전 1에만 적용됩니다. 이 구문은 버전 1 코드를 유지하기 위해서만 사용해야 합니다. 참조 [Classes and Structs](/visual-cpp/windows/classes-and-structs-cpp-component-extensions) 동등한 기능을 사용 하 여 새 구문에서에 대 한 내용은 합니다.  
  
 클래스를 \_\_value 형식으로 선언합니다.  
  
## 구문  
  
```  
  
__value  
 class-specifier  
__value  
 struct-specifier  
__nogc  
array-specifier  
__nogc  
pointer-specifier  
  
```  
  
## 설명  
 `__value` 형식 변수는 해당 데이터를 직접 포함하지만 관리되는 변수는 해당 데이터를 가리키며 이 데이터는 공용 언어 런타임 힙에 저장된다는 점에서 `__gc` 형식은 `__value` 형식과 다릅니다.  
  
 `__value` 형식에는 다음 조건이 적용됩니다.  
  
-   `__value` 키워드를 인터페이스에 적용할 수 없습니다.  
  
-   `__value` 형식은 개수 제한 없는 인터페이스에서 상속될 수 있으며 다른 형식이나 `__value` 형식에서는 상속될 수 없습니다.  
  
-   `__value` 형식은 정의에 의해 봉인됩니다. 자세한 내용은 [\_\_sealed](../misc/sealed.md)를 참조하십시오.  
  
-   관리되는 형식을 사용할 수 있는 모든 위치에 `__value` 형식을 사용할 수 있습니다.  
  
> [!NOTE]
>  `__value` 키워드는 `__abstract` 키워드와 함께 사용할 수 없습니다.  
  
 `__value` 형식을 명시적으로 **System::Object** 포인터에 연결할 수 있습니다. 이 프로세스를 boxing이라고 합니다.  
  
 `__nogc` 형식 안에 값 형식을 포함할 때 다음과 같은 지침이 적용됩니다.  
  
-   값 형식에는 **LayoutSequential** 또는 **LayoutExplicit**이 있어야 합니다.  
  
-   값 형식에는 포인터 멤버를 사용할 수 없습니다.  
  
-   값 형식에는 전용 데이터 멤버를 사용할 수 없습니다.  
  
 Managed Extensions for C\+\+에서 C\# 클래스와 C\# 구조체에 해당하는 요소는 다음과 같습니다.  
  
|Managed Extensions for C\+\+|C\#|추가 정보|  
|----------------------------------|---------|-----------|  
|\_\_gc 구조체<br /><br /> 또는<br /><br /> \_\_gc 클래스|클래스|[class](/dotnet/csharp/language-reference/keywords/class) 키워드|  
|\_\_value 구조체<br /><br /> 또는<br /><br /> \_\_value 클래스|struct|[struct](/dotnet/csharp/language-reference/keywords/struct) 키워드|  
  
## 예제  
 다음 예제에서는 `__value` 형식\(`V`\)을 선언하고 `__value` 형식의 인스턴스 두 개를 조작합니다.  
  
```  
// keyword__value.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value struct V {   
   int m_i;  
};  
  
int main() {  
   V v1, v2;  
   v1.m_i = 5;  
   v2 = v1;   // copies all fields of v1 to v2  
   v2.m_i = 6;   // does not affect v1.m_I  
}  
```