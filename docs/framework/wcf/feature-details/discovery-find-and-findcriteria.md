---
title: "Объекты обнаружения Find и FindCriteria | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99016fa4-1778-495b-b4cc-0e22fbec42c6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Объекты обнаружения Find и FindCriteria
Операция поиска объектов обнаружения инициируется клиентом для обнаружения одной или нескольких служб и является одним из основных действий, выполняемых при обнаружении.При операции поиска выполняется отправка сообщения зонда WS\-Discovery по сети.Службы, которые соответствуют указанному критерию, отвечают сообщениями WS\-Discovery ProbeMatch.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о сообщениях обнаружения см. в разделе [Спецификация WS\-Discovery](http://go.microsoft.com/fwlink/?LinkID=122347).  
  
## DiscoveryClient  
 Класс <xref:System.ServiceModel.Discovery.DiscoveryClient> обеспечивает механизм выполнения операции поиска и упрощает выполнение операций клиентов обнаружений.Он содержит метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, который выполняет операцию синхронного поиска с блокировкой, и метод <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>, который инициирует асинхронную операцию поиска без блокировки.Оба метода используют параметр <xref:System.ServiceModel.Discovery.FindCriteria> и передают результаты пользователю с помощью объекта <xref:System.ServiceModel.Discovery.FindResponse>.  
  
## FindCriteria  
 Параметр <xref:System.ServiceModel.Discovery.FindCriteria> имеет несколько свойств, которые могут быть сгруппированы в критерии поиска \(с указанием искомых служб\) и критерии прекращения поиска \(время выполнения поиска\).Параметр <xref:System.ServiceModel.Discovery.FindCriteria> может содержать несколько критериев поиска.По умолчанию служба должна соответствовать всем компонентам, в противном случае она не будет считаться службой, которая соответствует критериям.Если необходимо найти службы, которые соответствуют только части критериев, для службы можно реализовать пользовательскую логику поиска или использовать несколько критериев.  
  
 К критериям поиска относятся следующие.  
  
-   <xref:System.ServiceModel.Discovery.ContractTypeNames%2A> — необязательный.Имя контракта службы, поиск которой выполняется, и критерий, который обычно используется при поиске служб.Если указано несколько имен контрактов, будет получен ответ только от конечных точек службы, соответствующих всем контрактам.Обратите внимание, что в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] конечная точка поддерживает только один контракт.  
  
-   <xref:System.ServiceModel.Discovery.Scopes%2A> — необязательный.Области представляют собой абсолютные идентификаторы URI, которые используются для категоризации отдельных конечных точек служб.Их можно использовать в случаях, когда несколько конечных точек используется для предоставления одного контракта и необходим способ поиска подмножества конечных точек.Если указано более одной области, будет получен ответ только от конечных точек службы, соответствующих всем областям.  
  
-   Параметр <xref:System.ServiceModel.Discovery.ScopeMatchBy%2A> указывает алгоритм сопоставления, который используется для сопоставления областей в сообщении зонда с конечной точкой.Существует пять поддерживаемых правил сопоставления областей.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByExact%2A> выполняет базовое сравнение строк с учетом регистра.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix%2A> выполняет сопоставление по сегментам, разделенных символом «\/».При поиске http:\/\/contoso\/building1 было выполнено сопоставление со службой с областью http:\/\/contoso\/building\/floor1.Обратите внимание, что не было выполнено сопоставление с http:\/\/contoso\/building100 из\-за несоответствия двух последних сегментов.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByLdap%2A> сопоставляет области по сегментам с помощью URL\-адреса LDAP.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByUuid%2A> выполняет точное сопоставление областей с помощью строки UUID.  
  
    -   <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByNone%2A> выполняет сопоставление только тех служб, которые не указывают области.  
  
     Если правило сопоставления областей не указано, используется <xref:System.ServiceModel.Discovery.FindCriteria.ScopeMatchByPrefix%2A>.  
  
 К критериям прекращения относятся следующие.  
  
1.  <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> — максимальное значение времени ожидания ответов от служб в сети.Значение времени ожидания по умолчанию — 20 секунд.  
  
2.  <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> — максимальное количество ожидаемых ответов.Если ответы <xref:System.ServiceModel.Discovery.FindCriteria.MaxResults%2A> получены до истечения <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>, операция поиска завершается.  
  
## FindResponse  
 <xref:System.ServiceModel.Discovery.FindResponse> имеет свойство коллекции <xref:System.ServiceModel.Discovery.FindResponse.Endpoints%2A>, в котором содержатся все ответы, отправленные соответствующими службами в сети.Если ни одна служба не отправила ответ, коллекция пустая.Если ответила одна или несколько служб, все ответы сохраняются в объекте <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, в котором содержится адрес, контракт и дополнительные сведения о службе.  
  
 В следующем примере описывается выполнение операции поиска в коде.  
  
```  
// Create DiscoveryClient  
DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
// Create FindCriteria  
FindCriteria findCriteria = new FindCriteria(typeof(IPrinterService));  
findCriteria.Scopes.Add(new Uri("http://www.contoso.com/building1/floor1"));  
findCriteria.Duration = TimeSpan.FromSeconds(10);   
  
// Find ICalculatorService endpoints              
FindResponse findResponse = discoveryClient.Find(findCriteria);  
  
Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count)  
  
```  
  
## См. также  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [Использование клиентского канала обнаружения](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)   
 [Обнаружение с помощью областей](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)   
 [Асинхронная операция Find](../../../../docs/framework/wcf/samples/asynchronous-find-sample.md)   
 [Basic](../../../../docs/framework/wcf/samples/basic-sample.md)