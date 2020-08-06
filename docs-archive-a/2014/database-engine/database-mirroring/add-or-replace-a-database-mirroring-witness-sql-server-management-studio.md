---
title: Добавление или замена следящего сервера зеркального отображения базы данных (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87657300"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a>Добавление или замена следящего сервера зеркального отображения базы данных (среда SQL Server Management Studio)
  Если конечные точки зеркального отображения базы данных используют проверку подлинности Windows, для добавления или замены следящего сервера можно использовать среду [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] . Добавление следящего сервера в среде [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] изменяет текущий режим работы на режим высокого уровня безопасности с автоматической отработкой отказа.  
  
> [!NOTE]  
>  Настоятельно рекомендуется размещать следящий сервер на отдельном компьютере, не используемом ни одним из участников зеркального отображения. Учетная запись службы, используемая следящим сервером, должна располагаться в том же самом домене, что и учетные записи служб, используемые экземплярами основного и зеркального серверов, либо в доверенном домене.  
  
### <a name="to-add-or-replace-a-witness"></a>Добавление или замена следящего сервера  
  
1.  После подключения к экземпляру основного сервера в обозревателе объектов щелкните имя сервера, чтобы развернуть дерево сервера.  
  
2.  Разверните узел **Базы данных**и выберите основную базу данных сеанса, в котором добавляется или заменяется следящий сервер.  
  
3.  Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**. Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .  
  
4.  Щелкните **Настройка безопасности**.  
  
5.  Если появилось окно **Мастер настройки безопасности зеркального отображения баз данных** , нажмите кнопку **Далее**.  
  
6.  В диалоговом окне **Включение следящего сервера** установите переключатель **Да**и нажмите кнопку **Далее**.  
  
7.  В диалоговом окне **Выбор серверов для настройки** будет автоматически установлен флажок **Экземпляр следящего сервера** . Щелкните **Далее**.  
  
8.  В диалоговом окне **Экземпляр основного сервера** сохраните указанный порт и конечную точку. Щелкните **Далее**.  
  
9. В диалоговом окне **Экземпляр следящего сервера** нажмите кнопку **Соединить**.  
  
10. В диалоговом окне **Соединение с сервером** в поле **Имя сервера** укажите экземпляр следящего сервера и использование проверки подлинности Windows (по умолчанию). Нажмите кнопку **Соединить**.  
  
11. После установления соединения прослушиваемый порт и конечная точка зеркального отображения базы данных экземпляра следящего сервера отображаются в диалоговом окне **Экземпляр следящего сервера** . Щелкните **Далее**.  
  
12. Диалоговое окно **Учетные записи служб** содержит поля доменных серверных учетных записей основного, зеркального и следящего экземпляров сервера.  
  
    -   Если все экземпляры сервера используют одну и туже учетную запись, оставьте эти поля пустыми.  
  
    -   Если экземпляр следящего сервера использует не ту учетную запись, что другие участники, введите имя учетной записи в поля **Основной сервер**, **Зеркальный сервер**и **Следящий сервер** :  
  
         *ИМЯ_ДОМЕНА* **\\** *имя_пользователя*  
  
         Имя домена должно содержать только символы верхнего регистра.  
  
     Щелкните **Далее**.  
  
13. В итоговом окне **Завершение работы мастера** , в случае необходимости, проверьте конфигурацию следящего сервера и нажмите кнопку **Готово**.  
  
14. По завершении работы этот мастер возвращает в диалоговом окне **Свойства базы данных** сетевой адрес экземпляра следящего сервера, содержащийся в поле **Следящий сервер** . Кроме того, автоматически выбирается режим **Высокая безопасность с автоматической отработкой отказа (синхронно)** , который необходим при работе со следящим сервером.  
  
     Чтобы начать работу следящего сервера и изменить текущий режим работы на режим высокого уровня безопасности с автоматической отработкой отказа, нажмите кнопку **ОК**.  
  
## <a name="see-also"></a>См. также:  
 [Database Mirroring Witness](database-mirroring-witness.md)   
 [Зеркальное отображение базы данных (SQL Server)](database-mirroring-sql-server.md)   
 [Свойства базы данных (страница "Зеркальное отображение")](../../relational-databases/databases/database-properties-mirroring-page.md)   
 [Создание сеанса зеркального отображения базы данных с использованием проверки подлинности Windows (среда SQL Server Management Studio)](establish-database-mirroring-session-windows-authentication.md)   
 [Следящий сервер зеркального отображения базы данных](database-mirroring-witness.md)  
  
  