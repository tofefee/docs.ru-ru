---
title: Создание объекта DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 1ede51ed9119051a647fd27d8d02cd2c93e61bbb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510041"
---
# <a name="creating-a-datareader"></a>Создание объекта DataReader
Классы <xref:System.Data.DataTable> и <xref:System.Data.DataSet> имеют метод <xref:System.Data.DataTable.CreateDataReader%2A>, возвращающий содержимое объекта <xref:System.Data.DataTable> или содержимое объекта <xref:System.Data.DataSet> коллекции <xref:System.Data.DataSet.Tables%2A> в виде одного или нескольких доступных для чтения результирующих наборов с последовательным доступом.  
  
## <a name="example"></a>Пример  
 Следующее приложение командной строки создает экземпляр <xref:System.Data.DataTable>. В примере затем заполненный <xref:System.Data.DataTable> процедура, которая вызывает <xref:System.Data.DataTable.CreateDataReader%2A> метод, который выполняет проход по результатам, содержащимся в <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 В этом примере в окне консоли отображаются следующие выходные данные:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [Объекты DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
