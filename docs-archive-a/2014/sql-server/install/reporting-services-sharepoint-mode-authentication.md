---
title: Reporting Services проверки подлинности в режиме интеграции с SharePoint | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade SharePoint Mode [Reporting Services]
- SharePoint integration
- SharePoint Mode
ms.assetid: 2c19794a-dd55-4fe5-b901-6dd93e9f6beb
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 3b1316a1a49726ab0754f39160125425fec116d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87737535"
---
# <a name="reporting-services-sharepoint-mode-authentication"></a><span data-ttu-id="bae32-102">проверка подлинности служб Reporting Services в режиме SharePoint</span><span class="sxs-lookup"><span data-stu-id="bae32-102">Reporting Services SharePoint Mode Authentication</span></span>
  <span data-ttu-id="bae32-103">На странице **Проверка подлинности служб Reporting Services в режиме SharePoint** мастера установки [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] указываются учетные данные учетной записи службы, используемые в текущей установке служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bae32-103">Use the **Reporting Services SharePoint Mode Authentication** page of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Installation Wizard to specify the credentials of the service account that is used in the current [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation.</span></span> <span data-ttu-id="bae32-104">Эти учетные данные будут использованы для создания нового пула приложений SharePoint.</span><span class="sxs-lookup"><span data-stu-id="bae32-104">The credentials will be used to create a new SharePoint application pool.</span></span> <span data-ttu-id="bae32-105">Кроме того, будет создано новое приложение службы SharePoint для служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bae32-105">Also, one new [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] SharePoint service application will be created.</span></span> <span data-ttu-id="bae32-106">Имя приложения службы будет содержать имя предыдущего экземпляра [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bae32-106">The service application name will contain the name of the previous [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] instance name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="bae32-107">Варианты</span><span class="sxs-lookup"><span data-stu-id="bae32-107">Options</span></span>  
  
-   <span data-ttu-id="bae32-108">Параметр **Имя учетной записи пула приложений служб SSRS:** доступен только для чтения.</span><span class="sxs-lookup"><span data-stu-id="bae32-108">The **SSRS Application Pool Account Name:** option is read only.</span></span> <span data-ttu-id="bae32-109">Его значение автоматически заполняется текущим значением из существующей установки служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] , обновление которой производится.</span><span class="sxs-lookup"><span data-stu-id="bae32-109">The value is automatically populated with the current value from the existing [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] installation that you are upgrading.</span></span>  
  
-   <span data-ttu-id="bae32-110">Параметр **Пароль учетной записи пула приложений служб SSRS:** будет отключен, если эта учетная запись не требует пароля.</span><span class="sxs-lookup"><span data-stu-id="bae32-110">The **SSRS Application Pool Account Password:** option will be disabled if the application pool account does not require a password.</span></span> <span data-ttu-id="bae32-111">Например, "NT Authority\NetworkService".</span><span class="sxs-lookup"><span data-stu-id="bae32-111">For example, "NT Authority\NetworkService".</span></span> <span data-ttu-id="bae32-112">Если учетная запись пула приложений не требует пароля, то обновление нельзя будет продолжить до тех пор, пока не будет правильно введен пароль.</span><span class="sxs-lookup"><span data-stu-id="bae32-112">If the application pool account does require a password, you cannot continue with upgrade until you type the correct password.</span></span>  
  
 <span data-ttu-id="bae32-113">Дополнительные сведения см. в разделе [обновление и миграция Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) ( https://go.microsoft.com/fwlink/?LinkID=245628) .</span><span class="sxs-lookup"><span data-stu-id="bae32-113">For more information, see [Upgrade and Migrate Reporting Services](https://go.microsoft.com/fwlink/?LinkID=245628) (https://go.microsoft.com/fwlink/?LinkID=245628).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bae32-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="bae32-114">See Also</span></span>  
 [<span data-ttu-id="bae32-115">Обновление и перенос служб Reporting Services</span><span class="sxs-lookup"><span data-stu-id="bae32-115">Upgrade and Migrate Reporting Services</span></span>](https://go.microsoft.com/fwlink/?LinkID=245628)  
  
  
