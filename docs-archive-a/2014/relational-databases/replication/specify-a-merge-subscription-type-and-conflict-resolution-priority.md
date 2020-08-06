---
title: Укажите тип подписки на публикацию слиянием и приоритет разрешения конфликтов (SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- merge replication conflict resolution [SQL Server replication], merge subscription resolvers
- conflict resolution [SQL Server replication], merge replication
ms.assetid: 2b828d83-2341-4924-b92a-4f81a22246c0
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a19ae6246fe59308283fbaf2f35e2c49f96b140c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87752107"
---
# <a name="specify-a-merge-subscription-type-and-conflict-resolution-priority-sql-server-management-studio"></a>Указание типа подписки на публикацию слиянием и приоритета устранения конфликтов (среда SQL Server Management Studio)
  Задание типа и приоритета разрешения конфликтов для подписки на публикацию слиянием осуществляется на странице **Тип подписки** мастера создания подписки. Дополнительные сведения об использовании этого мастера см. в разделе [Create a Pull Subscription](create-a-pull-subscription.md) и [Create a Push Subscription](create-a-push-subscription.md).  
  
 После создания подписки нельзя изменить ее тип, но для типа серверной подписки можно изменить приоритет в диалоговом окне **Свойства подписки — \<Publisher>: \<PublicationDatabase>** . Дополнительные сведения о доступе к этому диалоговому окну см. в разделах [Просмотр и изменение свойств принудительной подписки](view-and-modify-push-subscription-properties.md) и [Просмотр и изменение свойств подписки по запросу](view-and-modify-pull-subscription-properties.md).  
  
### <a name="to-specify-a-merge-subscription-type-and-conflict-resolution-priority"></a>Указание типа подписки на публикацию слиянием и приоритета разрешения конфликтов  
  
1.  На странице **Тип подписки** мастера создания подписки выберите **Клиент** или **Сервер** в качестве значения параметра **Тип подписки** .  
  
2.  Если выбран тип подписки **Сервер**, введите также значение (от 0.00 до 99.99) для параметра **Приоритет разрешения конфликтов** .  
  
### <a name="to-modify-the-conflict-resolution-priority"></a>Изменение приоритета разрешения конфликтов  
  
1.  В диалоговом окне **Свойства подписки — \<Publisher>: \<PublicationDatabase>** в издателе введите значение (от 0,00 до 99,99) для параметра **Приоритет**.  
  
2.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a>См. также:  
 [Advanced Merge Replication Conflict Detection and Resolution](merge/advanced-merge-replication-conflict-detection-and-resolution.md)   
 [Подписка на публикации](subscribe-to-publications.md)  
  
  
