---
title: "Расширяемые объекты | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "расширяемые объекты [WCF]"
ms.assetid: bc88cefc-31fb-428e-9447-6d20a7d452af
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Расширяемые объекты
Шаблон расширяемого объекта используется для расширения существующих классов среды выполнения при помощи новых функций или добавления нового состояния к объекту.  Расширения, привязанные к одному из расширяемых объектов, позволяют использовать поведения на различных этапах обработки для получения доступа к общему состоянию и функциональности, привязанным к общему расширяемому объекту, к которому они могут получить доступ.  
  
## Шаблон IExtensibleObject\<T\>  
 Предусмотрено три интерфейса в шаблоне расширяемого объекта: <xref:System.ServiceModel.IExtensibleObject%601>, <xref:System.ServiceModel.IExtension%601> и <xref:System.ServiceModel.IExtensionCollection%601>.  
  
 Интерфейс <xref:System.ServiceModel.IExtensibleObject%601> реализуется типами, которые позволяют объектам <xref:System.ServiceModel.IExtension%601> настроить свою функциональность.  
  
 Расширяемые объекты обеспечивают динамическое агрегирование объектов <xref:System.ServiceModel.IExtension%601>.  Объекты <xref:System.ServiceModel.IExtension%601> характеризуются следующим интерфейсом:  
  
```  
public interface IExtension<T>  
where T : IExtensibleObject<T>  
{  
    void Attach(T owner);  
    void Detach(T owner);  
}  
```  
  
 Ограничение типов гарантирует, что расширения можно определить только для классов <xref:System.ServiceModel.IExtensibleObject%601>.  Методы<xref:System.ServiceModel.IExtension%601.Attach%2A> и <xref:System.ServiceModel.IExtension%601.Detach%2A> предоставляют уведомление об агрегировании или деагрегировании.  
  
 Реализации могут ограничивать, если их можно добавить и удалить из владельца.  Например, можно полностью запретить удаление, запретить добавление или удаление расширений, когда владелец или расширение находится в определенном состоянии, запретить одновременное добавление в несколько владельцев или разрешить только одно добавление с последующим одним удалением.  
  
 В шаблоне <xref:System.ServiceModel.IExtension%601> не подразумевается никаких взаимодействий с другими стандартными управляемыми интерфейсами.  В частности, метод <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> в объекте владельца, как правило, не отсоединяет его расширения.  
  
 При добавлении расширения в коллекцию метод <xref:System.ServiceModel.IExtension%601.Attach%2A> вызывается до того, как она поступает в коллекцию. При удалении расширения из коллекции метод <xref:System.ServiceModel.IExtension%601.Detach%2A> вызывается после ее удаления. Это значит \(предполагая соответствующую синхронизацию\), что расширение можно найти в коллекции, только в промежутке времени между вызовом метода <xref:System.ServiceModel.IExtension%601.Attach%2A> и метода <xref:System.ServiceModel.IExtension%601.Detach%2A>.  
  
 Нет необходимости, чтобы объект, переданный методу <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> или методу <xref:System.ServiceModel.IExtensionCollection%601.Find%2A>, был объектом <xref:System.ServiceModel.IExtension%601> \(например, можно передать любой объект\), но возвращенное расширение должно быть расширением <xref:System.ServiceModel.IExtension%601>.  
  
 Если ни одно из расширений в коллекции не является расширением <xref:System.ServiceModel.IExtension%601>, метод <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> возвращает значение null, а метод <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A> возвращает пустую коллекцию. Если несколько расширений реализуют <xref:System.ServiceModel.IExtension%601>, метод <xref:System.ServiceModel.IExtensionCollection%601.Find%2A> возвращает одно из них.  Значение, возвращаемое методом <xref:System.ServiceModel.IExtensionCollection%601.FindAll%2A>, является моментальным снимком.  
  
 Имеется два основных сценария.  В первом сценарии свойство <xref:System.ServiceModel.IExtensibleObject%601.Extensions%2A> используется как основанный на типах словарь для вставки состояния в объект с целью предоставления другому компоненту возможности просматривать его с помощью типа.  
  
 Во втором сценарии свойства <xref:System.ServiceModel.IExtension%601.Attach%2A> и <xref:System.ServiceModel.IExtension%601.Detach%2A> используются для предоставления объекту возможности участвовать в пользовательском поведении, таком как регистрация событий, наблюдение за переходами между состояниями и т. д.  
  
 Интерфейс <xref:System.ServiceModel.IExtensionCollection%601> \- это коллекция объектов <xref:System.ServiceModel.IExtension%601>, которая позволяет получить экземпляр <xref:System.ServiceModel.IExtension%601> по его типу.  Метод <xref:System.ServiceModel.IExtensionCollection%601.Find%2A?displayProperty=fullName> возвращает последний добавленный объект <xref:System.ServiceModel.IExtension%601> данного типа.  
  
### Расширяемые объекты в Windows Communication Foundation  
 Существуют четыре расширяемых объекта в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
-   <xref:System.ServiceModel.ServiceHostBase>. Это базовый класс для узла службы.  Расширения этого класса можно использовать для расширения поведения самого класса <xref:System.ServiceModel.ServiceHostBase> или для хранения состояния для каждой службы.  
  
-   <xref:System.ServiceModel.InstanceContext>. Этот класс соединяет экземпляр типа службы и среду выполнения службы.  В нем содержится информация об экземпляре, а также ссылка на класс <xref:System.ServiceModel.ServiceHostBase>, содержащий класс <xref:System.ServiceModel.InstanceContext>.  Расширения этого класса можно использовать для расширения поведения самого класса <xref:System.ServiceModel.InstanceContext> или для хранения состояния для каждой службы.  
  
-   <xref:System.ServiceModel.OperationContext>. Этот класс представляет данные об операциях, собранные средой выполнения для каждой операции.  Сюда входят такие данные как заголовки входящих сообщений, свойства входящих сообщений, идентификация входящих сообщений и др.  Расширения этого класса можно использовать как для расширения поведения класса <xref:System.ServiceModel.OperationContext>, так и для хранения состояния для каждой операции.  
  
-   <xref:System.ServiceModel.IContextChannel>. Этот интерфейс обеспечивает проверку каждого состояния для каналов и прокси\-серверов, созданных в среде выполнения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Расширения этого класса можно использовать как для расширения поведения класса <xref:System.ServiceModel.IClientChannel>, так и для хранения состояния для каждого канала.  
  
 В следующем примере кода показано использование простого расширения для отслеживания объектов <xref:System.ServiceModel.InstanceContext>.  
  
 [!code-csharp[IInstanceContextInitializer#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/iinstancecontextinitializer/cs/initializer.cs#1)]  
  
## См. также  
 <xref:System.ServiceModel.IExtensibleObject%601>   
 <xref:System.ServiceModel.IExtension%601>   
 <xref:System.ServiceModel.IExtensionCollection%601>