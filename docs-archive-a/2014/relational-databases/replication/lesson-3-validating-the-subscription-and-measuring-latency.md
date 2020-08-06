---
title: Занятие 3. Проверка подписки и измерение задержки | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: 147f7b93-1804-4e0b-9e17-57a51d035b2a
author: rothja
ms.author: jroth
ms.openlocfilehash: e4893c054d25d131eb2f88f32291606b0b789af7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87739695"
---
# <a name="lesson-3-validating-the-subscription-and-measuring-latency"></a>Занятие 3. Проверка подписки и измерение задержки
  На этом занятии изучаются трассировочные токены для проверки реплицируемых для подписчика изменений и определения задержки, т.е. времени, когда изменение, внесенное на стороне издателя, должно перейти на сторону подписчика. Приступать к этому занятию нужно только по завершении предыдущего: [Занятие 2. Создание подписки на публикацию транзакций](lesson-2-creating-a-subscription-to-the-transactional-publication.md).  
  
### <a name="to-insert-a-tracer-token-and-view-information-on-the-token"></a>Вставка трассировочного токена и просмотр сведений о токене  
  
1.  Подключитесь к издателю в среде [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], разверните узел сервера, щелкните правой кнопкой мыши папку **Репликация** и выберите пункт **Запустить монитор репликации**.  
  
     Запустится монитор репликации.  
  
2.  Раскройте группу издателей на левой панели, затем экземпляр издателя и выберите публикацию **AdvWorksProductTrans** .  
  
3.  Щелкните вкладку **Трассировочные токены** .  
  
4.  Выберите команду **Вставить трассировочный маркер**.  
  
5.  Просмотрите затраченное время для трассировочного маркера в следующих столбцах: **От издателя к распространителю**, **От распространителя к подписчику**, **Общая задержка**. Значение **Pending** указывает, что маркер не достиг данной точки.  
  
## <a name="next-steps"></a>Next Steps  
 На этом занятии показывается, как использовать трассировочные токены для проверки изменений, реплицируемых от издателя подписчику. Кроме того, показывается, как вставлять, обновлять и удалять данные из таблицы **Product** на стороне издателя и строить запрос к таблице **Product** на стороне подписчика для проверки изменений после репликации.  
  
 На этом учебник «Репликация данных между постоянно соединенными серверами» завершается. Похожий учебник, использующий репликацию слиянием, см. в разделе [Tutorial: Replicating Data with Mobile Clients](tutorial-replicating-data-with-mobile-clients.md).  
  
## <a name="see-also"></a>См. также:  
 [Измерение задержки и проверка правильности соединений для репликации транзакций](monitor/measure-latency-and-validate-connections-for-transactional-replication.md)  
  
  