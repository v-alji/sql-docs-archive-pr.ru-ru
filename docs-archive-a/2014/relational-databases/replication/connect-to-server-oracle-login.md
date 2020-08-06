---
title: Соединение с сервером, вкладка "Имя входа" (Oracle) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.login.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 86ed91a1-a07c-46f2-a913-67317ef2255e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 23f5b515fcb1e80416d860e2ff3a2e6be5431819
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655086"
---
# <a name="connect-to-server-oracle-login"></a><span data-ttu-id="e6940-102">Диалоговое окно «Соединение с сервером (Oracle)», вкладка «Имя входа»</span><span class="sxs-lookup"><span data-stu-id="e6940-102">Connect to Server (Oracle), Login</span></span>
  <span data-ttu-id="e6940-103">Вкладка **Имя входа** диалогового окна **Соединение с сервером** используется для задания учетной записи, с помощью которой будут осуществляться подключения распространителя [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] к издателю Oracle.</span><span class="sxs-lookup"><span data-stu-id="e6940-103">Use the **Login** tab of the **Connect to Server** dialog box to specify the account under which connections are made from the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor to the Oracle Publisher.</span></span> <span data-ttu-id="e6940-104">Должна использоваться та же учетная запись, что и заданная для схемы пользователя-администратора репликации в процессе настройки издателя.</span><span class="sxs-lookup"><span data-stu-id="e6940-104">You must use the same account as the one specified for the replication administrative user schema during configuration of the Publisher.</span></span> <span data-ttu-id="e6940-105">Дополнительные сведения см. в статье [Настройка издателя Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="e6940-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e6940-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6940-106">Options</span></span>  
 <span data-ttu-id="e6940-107">**Экземпляр сервера**</span><span class="sxs-lookup"><span data-stu-id="e6940-107">**Server instance**</span></span>  
 <span data-ttu-id="e6940-108">Имя TNS (Transparent Network Substrate) издателя Oracle, заданное в процессе настройки клиентского программного обеспечения Oracle, установленного у распространителя.</span><span class="sxs-lookup"><span data-stu-id="e6940-108">The Transparent Network Substrate (TNS) name of the Oracle Publisher, which is specified during configuration of the Oracle client software installed on the Distributor.</span></span>  
  
 <span data-ttu-id="e6940-109">**Аутентификация**</span><span class="sxs-lookup"><span data-stu-id="e6940-109">**Authentication**</span></span>  
 <span data-ttu-id="e6940-110">Для выбора доступны **Стандартная проверка подлинности Oracle** (рекомендуется) или **Проверка подлинности Windows**.</span><span class="sxs-lookup"><span data-stu-id="e6940-110">Select **Oracle Standard Authentication** (recommended) or **Windows Authentication**.</span></span> <span data-ttu-id="e6940-111">Если выбрана **Проверка подлинности Windows**:</span><span class="sxs-lookup"><span data-stu-id="e6940-111">If you select **Windows Authentication**:</span></span>  
  
-   <span data-ttu-id="e6940-112">Сервер Oracle должен быть настроен таким образом, чтобы принимать соединения, использующие учетные данные Windows.</span><span class="sxs-lookup"><span data-stu-id="e6940-112">The Oracle server must be configured to allow connections using Windows credentials.</span></span> <span data-ttu-id="e6940-113">Дополнительные сведения см. в документации Oracle.</span><span class="sxs-lookup"><span data-stu-id="e6940-113">For more information, see the Oracle documentation.</span></span>  
  
-   <span data-ttu-id="e6940-114">Необходимо в данный момент находиться в системе под той же учетной записью [!INCLUDE[msCoName](../../includes/msconame-md.md)] , что и заданная в схеме пользователя-администратора репликации.</span><span class="sxs-lookup"><span data-stu-id="e6940-114">You must be currently logged in with the same [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows account you specified for the replication administrative user schema.</span></span>  
  
 <span data-ttu-id="e6940-115">**Имя** и **Пароль**</span><span class="sxs-lookup"><span data-stu-id="e6940-115">**Login** and **Password**</span></span>  
 <span data-ttu-id="e6940-116">Если выбрана **Стандартная проверка подлинности Oracle** в качестве параметра **Проверка подлинности** , необходимо задать имя и пароль, которые должны совпадать с заданными в схеме пользователя-администратора репликациями.</span><span class="sxs-lookup"><span data-stu-id="e6940-116">If you selected **Oracle Standard Authentication** for the **Authentication** option, specify the login and password to use, which must be the same as those specified for the replication administrative user schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6940-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="e6940-117">See Also</span></span>  
 [<span data-ttu-id="e6940-118">Глоссарий терминов по публикации Oracle</span><span class="sxs-lookup"><span data-stu-id="e6940-118">Glossary of Terms for Oracle Publishing</span></span>](non-sql/glossary-of-terms-for-oracle-publishing.md)  
  
  
