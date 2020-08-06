---
title: Повышение транзакции | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- distributed transactions [CLR integration]
- promoting transactions [CLR integration]
- Enlist keyword
- transaction promotion [CLR integration]
ms.assetid: 5bc7e26e-28ad-4198-a40d-8b2c648ba304
author: rothja
ms.author: jroth
ms.openlocfilehash: e78cbb3d2fc888e56c0b55780daf7b449fe6dc40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87751187"
---
# <a name="transaction-promotion"></a>Повышение транзакции
  *Повышение* транзакции описывает упрощенную локальную транзакцию, которую можно автоматически повысить до полностью распространяемой транзакции по мере необходимости. Когда управляемая хранимая процедура запускается в рамках транзакции базы данных на сервере, в контексте локальной транзакции запускается код CLR.  Если соединение с удаленным сервером открывается в рамках транзакции базы данных, это соединение с удаленным сервером прикрепляется к распределенной транзакции, а локальная транзакция автоматически повышается до распределенной транзакции. Таким образом повышение транзакции минимизирует избыток распределенных транзакций, откладывая создание распределенной транзакции до тех пор, пока в ней не возникнет необходимость. Повышение транзакций выполняется автоматически, если оно задано с помощью ключевого слова `Enlist`, и не требует вмешательства разработчика. Поставщик данных .NET Framework для [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] обеспечивает поддержку повышения транзакций с помощью классов в пространстве имен .NET Framework `System.Data.SqlClient`.  
  
## <a name="the-enlist-keyword"></a>Ключевое слово Enlist  
 Свойство `ConnectionString` объекта `SqlConnection` поддерживает использование ключевого слова `Enlist`, которое указывает, будет ли клиент `System.Data.SqlClient` обнаруживать контексты транзакций и автоматически прикреплять соединение к распределенной транзакции. Если для этого ключевого слова задано значение true (по умолчанию), соединение автоматически прикрепляется к текущему контексту транзакции открывающего потока. Если для этого ключевого слова задано значение false, то соединение SqlClient не будет взаимодействовать с распределенной транзакцией. Если ключевое слово `Enlist` в строке соединения не задано, то соединение автоматически прикрепляется к распределенной транзакции, если она будет обнаружена при открытии соединения.  
  
## <a name="distributed-transactions"></a>Распределенные транзакции  
 Распределенные транзакции обычно потребляют значительные системные ресурсы. [!INCLUDE[msCoName](../../includes/msconame-md.md)]Координатор распределенных транзакций (MS DTC) управляет такими транзакциями и интегрирует все диспетчеры ресурсов, к которым осуществляется доступ в этих транзакциях. С другой стороны, повышение транзакции – это особая форма транзакции `System.Transactions`, эффективно делегирующей работу простой транзакции [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Пространство имен `System.Transactions`, клиент `System.Data.SqlClient` и [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] координируют работу, выполняемую при обработке транзакции, при необходимости повышая ее до полностью распределенной транзакции.  
  
 Преимущество использования повышения транзакций заключается в том, что при открытии соединения с активной транзакцией `TransactionScope` и отсутствии других открытых соединений, такая транзакция фиксируется как упрощенная, что позволяет избежать излишних затрат ресурсов на полностью распределенную транзакцию. Дополнительные сведения о `TransactionScope` см. [в разделе Использование System. Transactions](../native-client-ole-db-transactions/transactions.md).  
  
## <a name="see-also"></a>См. также:  
 [Интеграция со средой CLR и транзакции](clr-integration-and-transactions.md)  
  
  