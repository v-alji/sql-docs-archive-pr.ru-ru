---
title: Учетные данные Oracle для выполнения скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 683b313e5b1065c3709c4637ddf968641612cc0b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87728582"
---
# <a name="oracle-credentials-for-running-script"></a><span data-ttu-id="58862-102">Учетные данные Oracle для выполнения скрипта</span><span class="sxs-lookup"><span data-stu-id="58862-102">Oracle Credentials for Running Script</span></span>
  <span data-ttu-id="58862-103">Чтобы запустить скрипт дополнительного журналирования Oracle из консоли конструктора CDC Oracle, программа запрашивает учетные данные пользователя Oracle, запускающего скрипт.</span><span class="sxs-lookup"><span data-stu-id="58862-103">To run the Oracle supplemental logging script from the Oracle CDC Designer console, the program prompts you for the credentials of the Oracle user who is running the script.</span></span> <span data-ttu-id="58862-104">Чтобы запустить этот скрипт, пользователь Oracle должен иметь разрешение ALTER TABLE для всех таблиц, которые будут отслеживаться, а также разрешение SELECT на представление DBA_LOG_GROUPS.</span><span class="sxs-lookup"><span data-stu-id="58862-104">To run this script, the Oracle user must have ALTER TABLE permission for all the tables to be captured and SELECT permission on the DBA_LOG_GROUPS view.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="58862-105">Список задач</span><span class="sxs-lookup"><span data-stu-id="58862-105">Task List</span></span>  
 <span data-ttu-id="58862-106">Введите в этом диалоговом окне следующие данные:</span><span class="sxs-lookup"><span data-stu-id="58862-106">Enter the following in this dialog box:</span></span>  
  
 <span data-ttu-id="58862-107">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="58862-107">**Authentication**</span></span>  
  
 <span data-ttu-id="58862-108">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="58862-108">Select one of the following:</span></span>  
  
-   <span data-ttu-id="58862-109">**Проверка подлинности Windows**. Выберите этот параметр, чтобы использовать учетные данные текущего пользователя Windows.</span><span class="sxs-lookup"><span data-stu-id="58862-109">**Windows Authentication**: Select this to use the current Windows domain credentials.</span></span> <span data-ttu-id="58862-110">Этот параметр можно использовать только в том случае, если в базе данных Oracle настроено использование проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="58862-110">You can use this option only if the Oracle database is configured to work with Windows authentication.</span></span>  
  
-   <span data-ttu-id="58862-111">**Проверка подлинности Oracle**. Если выбран этот вариант, то нужно будет ввести **Имя пользователя** и **Пароль** пользователя в исходной базе данных Oracle, с которой устанавливается соединение.</span><span class="sxs-lookup"><span data-stu-id="58862-111">**Oracle Authentication**: If you select this option, you must type the **User Name** and **Password** for the user in the Source Oracle database you are connecting to.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58862-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="58862-112">See Also</span></span>  
 <span data-ttu-id="58862-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span><span class="sxs-lookup"><span data-stu-id="58862-113">[How to Manage a CDC Instance](manage-a-cdc-instance.md) </span></span>  
 [<span data-ttu-id="58862-114">Обзор и создание скриптов дополнительного журналирования</span><span class="sxs-lookup"><span data-stu-id="58862-114">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
