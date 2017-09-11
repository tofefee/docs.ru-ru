---
title: "Ковариация и контрвариантность (Visual Basic)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 775e4512a5ff31c7059961f6332c6bdc0dc5247a
ms.openlocfilehash: 8d31737fc3d02c9caa4c13ef2d69e5e3192ef3af
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---
# <a name="covariance-and-contravariance-visual-basic"></a><span data-ttu-id="fa495-102">Ковариация и контрвариантность (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-102">Covariance and Contravariance (Visual Basic)</span></span>
<span data-ttu-id="fa495-103">В Visual Basic ковариация и контрвариантность позволяют использовать неявное преобразование ссылок для типов массивов и делегатов, а также для аргументов универсального типа.</span><span class="sxs-lookup"><span data-stu-id="fa495-103">In Visual Basic, covariance and contravariance enable implicit reference conversion for array types, delegate types, and generic type arguments.</span></span> <span data-ttu-id="fa495-104">Ковариация сохраняет совместимость присваивания, а при контрвариантности присваивание начинает работать противоположным образом.</span><span class="sxs-lookup"><span data-stu-id="fa495-104">Covariance preserves assignment compatibility and contravariance reverses it.</span></span>  
  
 <span data-ttu-id="fa495-105">Следующий код показывает разницу между совместимостью присваивания, ковариацией и контрвариантностью.</span><span class="sxs-lookup"><span data-stu-id="fa495-105">The following code demonstrates the difference between assignment compatibility, covariance, and contravariance.</span></span>  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 <span data-ttu-id="fa495-106">Ковариация для массивов позволяет неявно преобразовать массив более производного типа в массив менее производного типа.</span><span class="sxs-lookup"><span data-stu-id="fa495-106">Covariance for arrays enables implicit conversion of an array of a more derived type to an array of a less derived type.</span></span> <span data-ttu-id="fa495-107">Но эта операция не является типобезопасной, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="fa495-107">But this operation is not type safe, as shown in the following code example.</span></span>  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 <span data-ttu-id="fa495-108">Поддержка ковариации и контрвариантности для групп методов позволяет сопоставить сигнатуры методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="fa495-108">Covariance and contravariance support for method groups allows for matching method signatures with delegate types.</span></span> <span data-ttu-id="fa495-109">За счет этого вы можете назначать делегатам не только методы с совпадающими сигнатурами, но и методы, которые возвращают более производные типы (ковариация) или принимают параметры с менее производными типами (контрвариантность), чем задает тип делегата.</span><span class="sxs-lookup"><span data-stu-id="fa495-109">This enables you to assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="fa495-110">Дополнительные сведения см. в разделах [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [Использование вариативности в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fa495-110">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="fa495-111">В следующем примере кода демонстрируется поддержка ковариации и контрвариантности для групп методов.</span><span class="sxs-lookup"><span data-stu-id="fa495-111">The following code example shows covariance and contravariance support for method groups.</span></span>  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 <span data-ttu-id="fa495-112">В .NET Framework 4 и более поздних версиях язык Visual Basic поддерживает ковариацию и контрвариантность для универсальных интерфейсов и делегатов, а также позволяет выполнять неявное преобразование параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="fa495-112">In .NET Framework 4 or later Visual Basic support covariance and contravariance in generic interfaces and delegates and allow for implicit conversion of generic type parameters.</span></span> <span data-ttu-id="fa495-113">Дополнительные сведения см. в разделах [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) и [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fa495-113">For more information, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) and [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
 <span data-ttu-id="fa495-114">В следующем примере кода показано неявное преобразование ссылок для универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="fa495-114">The following code example shows implicit reference conversion for generic interfaces.</span></span>  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 <span data-ttu-id="fa495-115">Универсальный интерфейс или делегат называется *вариантным*, если его универсальные параметры объявлены ковариантными или контрвариантными.</span><span class="sxs-lookup"><span data-stu-id="fa495-115">A generic interface or delegate is called *variant* if its generic parameters are declared covariant or contravariant.</span></span> <span data-ttu-id="fa495-116">Visual Basic позволяет вам создавать свои собственные вариантные интерфейсы и делегаты.</span><span class="sxs-lookup"><span data-stu-id="fa495-116">Visual Basic enables you to create your own variant interfaces and delegates.</span></span> <span data-ttu-id="fa495-117">Дополнительные сведения см. в разделах [Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) и [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fa495-117">For more information, see [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) and [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="fa495-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="fa495-118">Related Topics</span></span>  
  
|<span data-ttu-id="fa495-119">Заголовок</span><span class="sxs-lookup"><span data-stu-id="fa495-119">Title</span></span>|<span data-ttu-id="fa495-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fa495-120">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fa495-121">Вариативность в универсальных интерфейсах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-121">Variance in Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|<span data-ttu-id="fa495-122">В этом разделе описываются ковариация и контрвариация в универсальных интерфейсах, а также представлен список вариативных универсальных интерфейсов платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa495-122">Discusses covariance and contravariance in generic interfaces and provides a list of variant generic interfaces in the .NET Framework.</span></span>|  
|[<span data-ttu-id="fa495-123">Создание вариативных универсальных интерфейсов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-123">Creating Variant Generic Interfaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|<span data-ttu-id="fa495-124">Узнайте, как создавать ваши собственные вариантные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="fa495-124">Shows how to create custom variant interfaces.</span></span>|  
|[<span data-ttu-id="fa495-125">Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-125">Using Variance in Interfaces for Generic Collections (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|<span data-ttu-id="fa495-126">Узнайте, как использовать поддержку ковариации и контрвариантности в интерфейсах <xref:System.Collections.Generic.IEnumerable%601> и <xref:System.IComparable%601> для многократного использования кода.</span><span class="sxs-lookup"><span data-stu-id="fa495-126">Shows how covariance and contravariance support in the <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IComparable%601> interfaces can help you reuse code.</span></span>|  
|[<span data-ttu-id="fa495-127">Вариативность в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-127">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|<span data-ttu-id="fa495-128">Раздел описывает ковариацию и контрвариантность в универсальных и неуниверсальных делегатах, а также приводит список вариантных универсальных делегатов в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa495-128">Discusses covariance and contravariance in generic and non-generic delegates and provides a list of variant generic delegates in the .NET Framework.</span></span>|  
|[<span data-ttu-id="fa495-129">Использование вариативности в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-129">Using Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|<span data-ttu-id="fa495-130">Узнайте, как использовать поддержку ковариации и контрвариантности в неуниверсальных делегатах для сопоставления сигнатур методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="fa495-130">Shows how to use covariance and contravariance support in non-generic delegates to match method signatures with delegate types.</span></span>|  
|[<span data-ttu-id="fa495-131">Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fa495-131">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|<span data-ttu-id="fa495-132">Узнайте, как использовать поддержку ковариации и контрвариантности в делегатах `Func` и `Action` для многократного использования кода.</span><span class="sxs-lookup"><span data-stu-id="fa495-132">Shows how covariance and contravariance support in the `Func` and `Action` delegates can help you reuse code.</span></span>|
