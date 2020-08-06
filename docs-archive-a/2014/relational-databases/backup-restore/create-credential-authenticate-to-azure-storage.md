---
title: Создание учетных данных — аутентификация в хранилище Azure | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740073"
---
# <a name="create-credential---authenticate-to-azure-storage"></a>Создание учетных данных — проверка подлинности в хранилище Azure
  Чтобы создать учетные данные SQL, воспользуйтесь диалоговым окном **Резервное копирование по URL-адресу — создать учетные данные**.  
  
 При создании учетных данных с помощью этого диалогового окна необходимо предоставить сертификат управления Azure, добавленный в локальное хранилище сертификатов, или профиль публикации, скачанный на компьютер для проверки подписки и сведений об учетной записи хранения.  
  
 **Учетные данные SQL**  
 Задайте имя создаваемых учетных данных SQL.  
  
## <a name="azure-credentials"></a>Учетные данные Azure  
 **Сертификат управления**  
 Используйте этот параметр, чтобы указать сертификат из локального хранилища сертификатов, соответствующий сертификату управления из Azure. Дополнительные сведения о сертификате управления Azure см. в статье [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781) (Создание и передача сертификата управления для Azure).  
  
 **Подписка**  
 Выберите, введите или вставьте идентификатор подписки Azure, который соответствует сертификату управления из локального хранилища сертификатов.  
  
 **Профиль публикации**  
 Используйте этот параметр, если имеется профиль публикации, загруженный на компьютер. Если воспользоваться этим параметром, идентификатор подписки и сертификат будут заполнены автоматически.  
  
> [!CAUTION]  
>  SQL Server в настоящий момент поддерживает версию 2.0 профиля публикации. Для загрузки поддерживаемой версии профиля публикации см. раздел [Загрузка профиля публикации 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).  
  
## <a name="storage-account"></a>Учетная запись хранения  
 Выберите учетную запись хранения, которую нужно использовать для хранения файлов резервных копий.  
  
  