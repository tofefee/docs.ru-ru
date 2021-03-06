---
title: Выражения значения по умолчанию (руководство по программированию на C#)
description: Выражения значения по умолчанию создают значение по умолчанию для любого ссылочного типа или типа значения
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 94866f22fb3ad921a834cffb16fe17e44cef5965
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47192632"
---
# <a name="default-value-expressions-c-programming-guide"></a>Выражения значения по умолчанию (руководство по программированию на C#)

Выражение значения по умолчанию `default(T)` создает значение по умолчанию с типом `T`. В следующей таблице показаны значения, которые создаются для различных типов.

|Тип|Значение по умолчанию|
|---------|---------|
|любой ссылочный тип;|`null`|
|Тип числового значения|Нуль|
|[bool](../../language-reference/keywords/bool.md)|`false`|
|[char](../../language-reference/keywords/char.md)|`'\0'`|
|[enum](../../language-reference/keywords/enum.md)|Значение, создаваемое выражением `(E)0`, где `E` — это идентификатор перечисления.|
|[struct](../../language-reference/keywords/struct.md)|Значение, создаваемое путем установки значений по умолчанию для всех полей с типами значений и значений `null` для всех полей ссылочного типа.|
|Тип, допускающий значение NULL|Экземпляр, свойство `false` которого имеет значение <xref:System.Nullable%601.HasValue%2A>, а свойство <xref:System.Nullable%601.Value%2A> не определено.|

Выражения значения по умолчанию особенно полезны в универсальных классах и методах. Одна из проблем при использовании универсальных шаблонов связана с присваиванием значения по умолчанию параметризованного типа `T`, для которого заранее неизвестны следующие характеристики.

- Будет ли тип `T` ссылочным типом или типом значения.
- Если тип `T` является типом значения, будет ли это числовое значение или структура.

 При заданной переменной `t` параметризованного типа `T` оператор `t = null` действителен, только если `T` является ссылочным типом. Присваивание `t = 0` работает только для типов числовых значений, но не для структур. Чтобы решить этот вопрос, используйте выражение значения по умолчанию:

```csharp
T t = default(T);
```

Выражение `default(T)` не ограничивается универсальными классами и методами. Выражения значения по умолчанию можно использовать с любым управляемым типом. Любые из следующих выражений допустимы.

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 В следующем примере из класса `GenericList<T>` показано, как использовать оператор `default(T)` в универсальном классе. Дополнительные сведения см. в разделе [Введение в универсальные шаблоны](../generics/introduction-to-generics.md).

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Литерал по умолчанию и определение типа

Начиная с C# 7.1, литерал `default` может использоваться для выражений значения по умолчанию, если компилятор может вывести тип выражения. Литерал `default` создает то же значение, что и эквивалент `default(T)`, где `T` является выведенным типом. Это может сделать код более компактным за счет сокращения избыточности в случае неоднократного объявления типа. Литерал `default` может использоваться в любом из следующих расположений.

- инициализатор переменной
- назначение переменных
- объявление значения по умолчанию для необязательного параметра
- предоставление значения для аргумента вызова метода
- оператор return (или выражение в элементе в тексте выражения)

В следующем примере показано множество вариантов использования литерала `default` в выражении значения по умолчанию:

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic>  
- [Руководство по программированию на C#](../index.md)  
- [Универсальные шаблоны (Руководство по программированию на C#)](../generics/index.md)  
- [Универсальные методы](../generics/generic-methods.md)  
- [Универсальные шаблоны в .NET](~/docs/standard/generics/index.md)  
- [Таблица значений по умолчанию](../../language-reference/keywords/default-values-table.md)
