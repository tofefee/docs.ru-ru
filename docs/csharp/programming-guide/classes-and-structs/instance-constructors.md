---
title: Конструкторы экземпляров (Руководство по программированию в C#)
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: cd7105ec61e5c878dc148c30b27706b1eda3ae72
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530383"
---
# <a name="instance-constructors-c-programming-guide"></a>Конструкторы экземпляров (Руководство по программированию в C#)
Конструкторы экземпляров используются для создания и инициализации переменных члена экземпляра, если создание объекта [class](../../../csharp/language-reference/keywords/class.md) осуществляется с помощью выражения [new](../../../csharp/language-reference/keywords/new.md). Для инициализации класса [static](../../../csharp/language-reference/keywords/static.md) или статических переменных в нестатическом классе необходимо определить статический конструктор. Дополнительные сведения см. в разделе [Статические конструкторы](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).  
  
 В следующем примере показан конструктор экземпляра.  
  
 [!code-csharp[csProgGuideObjects#5](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_1.cs)]  
  
> [!NOTE]
>  Для ясности этот класс содержит открытые поля. Открытые поля не рекомендуется использовать на практике, поскольку в этом случае любой метод в любом месте программы получает неограниченный и неконтролируемый доступ к внутренней работе объекта. Члены данных обычно должны быть закрытыми, а доступ к ним должен осуществляться только посредством методов и свойства класса.  
  
 Этот конструктор экземпляра вызывается каждый раз при создании объекта на базе класса `CoOrds`. Такой конструктор без аргументов называется *конструктором по умолчанию*. Зачастую такие конструкторы используются для предоставления дополнительных конструкторов. Например, можно добавить конструктор в класс `CoOrds`, позволяющий указывать начальные значения для членов данных:  
  
 [!code-csharp[csProgGuideObjects#76](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_2.cs)]  
  
 Это позволяет создавать объекты `CoOrd` с начальными значениями по умолчанию или с другими начальными значениями:  
  
 [!code-csharp[csProgGuideObjects#77](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_3.cs)]  
  
 Если класс не содержит конструктор, автоматически создается конструктор по умолчанию, и для инициализации полей объекта используются значения по умолчанию. Например, [int](../../../csharp/language-reference/keywords/int.md) инициализируется значением 0. Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md). Следовательно, поскольку конструктор по умолчанию класса `CoOrds` инициализирует все члены данных с нулевыми значениями, его можно удалить, при этом порядок работы класса не изменится. Полный пример использования нескольких конструкторов см. в данном разделе в примере 1; пример автоматически созданного конструктора см. в примере 2.  
  
 Конструкторы экземпляров также можно использовать для вызова конструкторов экземпляров базового класса. Конструктор класса может вызвать конструктор базового класса с помощью инициализатора:  
  
 [!code-csharp[csProgGuideObjects#78](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_4.cs)]  
  
 В этом примере класс `Circle` передает значения радиуса и высоты конструктору, предоставленному классом `Shape`, для которого класс `Circle` является производным. Полный текст кода с использованием классов `Shape` и `Circle` см. в данном разделе в примере 3.  
  
## <a name="example-1"></a>Пример 1  
 В следующем примере демонстрируется класс с двумя конструкторами, один из которых не имеет аргументов, а второй имеет два аргумента.  
  
 [!code-csharp[csProgGuideObjects#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_5.cs)]  
  
## <a name="example-2"></a>Пример 2  
 В этом примере класс `Person` не имеет конструкторов, поэтому автоматически предоставляется конструктор по умолчанию, а все поля инициализируются со значениями по умолчанию.  
  
 [!code-csharp[csProgGuideObjects#8](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_6.cs)]  
  
 Обратите внимание, что значение по умолчанию `age` равно `0`, а значение по умолчанию `name` равно `null`. Дополнительные сведения о значениях по умолчанию см. в разделе [Таблица значений по умолчанию](../../../csharp/language-reference/keywords/default-values-table.md).  
  
## <a name="example-3"></a>Пример 3  
 В следующем примере демонстрируется использование инициализатора базового класса. Класс `Circle` является производным от основного класса `Shape`, а класс `Cylinder` является производным от класса `Circle`. Конструктор каждого производного класса использует инициализатор своего базового класса.  
  
 [!code-csharp[csProgGuideObjects#9](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/instance-constructors_7.cs)]  
  
 Дополнительные примеры вызова конструкторов базовых классов см. в разделах [virtual](../../../csharp/language-reference/keywords/virtual.md), [override](../../../csharp/language-reference/keywords/override.md) и [base](../../../csharp/language-reference/keywords/base.md).  
  
## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../../../csharp/programming-guide/index.md)  
- [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)  
- [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
- [Методы завершения](../../../csharp/programming-guide/classes-and-structs/destructors.md)  
- [static](../../../csharp/language-reference/keywords/static.md)
