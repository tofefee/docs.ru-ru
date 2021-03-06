---
title: Незапечатанные классы
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891381"
---
# <a name="unsealed-classes"></a>Незапечатанные классы
Запечатанные классы не может наследоваться от, а также предотвращают расширяемости. В противоположность этому классы, которые могут наследоваться от называются незапечатанные классы.  
  
 **✓ CONSIDER** использование незапечатанных классов с нет добавить виртуальный или защищенных членов, так как это отличный способ недорогого еще очень полезного расширяемость для платформу.  
  
 Разработчики часто должно производиться наследование незапечатанные классы таким образом, чтобы добавить членов удобства, таких как пользовательские конструкторы, новые методы или перегрузки метода. Например `System.Messaging.MessageQueue` не запечатан и таким образом позволяет пользователям создавать пользовательские очереди это значение по умолчанию для пути к определенной очереди или добавление пользовательских методов, которые упрощают API для конкретных сценариев.  
  
 Являются незапечатанных классов по умолчанию в большей части языков программирования, и это также рекомендуемый по умолчанию для большинства классов в платформ. Благодарим вас за пользователями framework и довольно недорого из-за сравнительно мало тестов затраты, связанные с незапечатанных типов, расширяемости, обеспечиваемый незапечатанных типов.  
  
 *Фрагменты: © Корпорация Майкрософт (Microsoft Corporation), 2005, 2009. Все права защищены.*  
  
 *Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*  
  
## <a name="see-also"></a>См. также

- [Рекомендации по проектированию на основе Framework](../../../docs/standard/design-guidelines/index.md)  
- [Разработка с обеспечением расширяемости](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Запечатывание](../../../docs/standard/design-guidelines/sealing.md)
