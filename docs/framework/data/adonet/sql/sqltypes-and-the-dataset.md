---
title: Типы SqlType и набор данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: fe00e669449d40320a2038697976423db83ade5b
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43511551"
---
# <a name="sqltypes-and-the-dataset"></a>Типы SqlType и набор данных
В ADO.NET 2.0 улучшена поддержка типов для объекта `DataSet` через пространство имен <xref:System.Data.SqlTypes>. Типы <xref:System.Data.SqlTypes> разработаны для предоставления типов данных с одинаковой семантикой и точностью в качестве типов данных в базе данных SQL Server. Каждому типу данных в пространстве имен <xref:System.Data.SqlTypes> соответствует эквивалентный тип данных в SQL Server с аналогичным базовым представлением данных.  
  
 Использование <xref:System.Data.SqlTypes> непосредственно в <xref:System.Data.DataSet> дает несколько преимуществ при работе с типами данных SQL Server. <xref:System.Data.SqlTypes> поддерживает ту же семантику, что и собственные типы данных SQL Server. Указание одного из типов <xref:System.Data.SqlTypes> в определении <xref:System.Data.DataColumn> позволяет избежать потери точности, которая может возникнуть при преобразовании десятичных или численных типов данных к одному из типов данных среды CLR.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере создается объект <xref:System.Data.DataTable>, явным образом определяющий типы данных <xref:System.Data.DataColumn> через типы <xref:System.Data.SqlTypes>, а не типы среды CLR. В этом коде таблица <xref:System.Data.DataTable> заполняется данными из таблицы Sales.SalesOrderDetail базы данных AdventureWorks на сервере SQL Server. В результатах, отображаемых в консольном окне, показывается тип данных каждого столбца, а также значения, полученные из SQL Server.  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также  
 [Сопоставления типов данных SQL Server](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)  
 [Настройка параметров и типы данных параметров](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
