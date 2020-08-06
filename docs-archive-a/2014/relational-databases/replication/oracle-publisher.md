---
title: Издатель Oracle | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newpubwizard.selectoraclepublisher.f1
ms.assetid: 019b7c49-dcca-445d-8969-5982a8ccbc1a
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: db52b93b3d260ff58a151e7238bbbe065bc47bc0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655064"
---
# <a name="oracle-publisher"></a><span data-ttu-id="d3589-102">Издатель Oracle</span><span class="sxs-lookup"><span data-stu-id="d3589-102">Oracle Publisher</span></span>
  <span data-ttu-id="d3589-103">Начиная с версии [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] позволяет публиковать данные из базы данных Oracle, используя репликацию моментальных снимков и репликацию транзакций.</span><span class="sxs-lookup"><span data-stu-id="d3589-103">Beginning with [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] allows you to publish data from an Oracle database using snapshot and transactional replication.</span></span> <span data-ttu-id="d3589-104">Дополнительные сведения см. в статье [Обзор публикации Oracle](non-sql/oracle-publishing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3589-104">For more information, see [Oracle Publishing Overview](non-sql/oracle-publishing-overview.md).</span></span>  
  
 <span data-ttu-id="d3589-105">Издатель Oracle должен использовать удаленный распространитель [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ; данный мастер должен быть запущен на этом сервере после установки и тестирования необходимого сетевого ПО Oracle.</span><span class="sxs-lookup"><span data-stu-id="d3589-105">The Oracle Publisher must use a remote [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor; this wizard must be run on that server after the necessary Oracle networking software has been installed and tested.</span></span> <span data-ttu-id="d3589-106">Дополнительные сведения см. в статье [Настройка издателя Oracle](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="d3589-106">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d3589-107">Если другой администратор настроил базу данных Oracle в качестве издателя, после нажатия кнопки **Далее** будет выбран запрос на ввод пароля для имени входа репликации, используемого для подключения к этой базе данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="d3589-107">If another administrator configured the Oracle database as a Publisher, after clicking **Next** you will be prompted to enter the password for the replication login used to connect to the Oracle database.</span></span> <span data-ttu-id="d3589-108">Затем[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] установит соответствие между именем входа и соединением связанного сервера с базой данных Oracle.</span><span class="sxs-lookup"><span data-stu-id="d3589-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will then create a mapping between your login and the linked server connection to the Oracle database.</span></span> <span data-ttu-id="d3589-109">При следующих соединениях с этой базой данных Oracle вводить пароль не потребуется.</span><span class="sxs-lookup"><span data-stu-id="d3589-109">You will not be required to enter a password for subsequent connections to the Oracle database.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d3589-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3589-110">Options</span></span>  
 <span data-ttu-id="d3589-111">**Издатели Oracle**</span><span class="sxs-lookup"><span data-stu-id="d3589-111">**Oracle Publishers**</span></span>  
 <span data-ttu-id="d3589-112">Выберите издатель Oracle из списка.</span><span class="sxs-lookup"><span data-stu-id="d3589-112">Select an Oracle Publisher from the list.</span></span> <span data-ttu-id="d3589-113">Этот список содержит издателей Oracle, ранее настроенных на использование данного сервера, к которому данный мастер обращается как к их распространителю.</span><span class="sxs-lookup"><span data-stu-id="d3589-113">This list contains Oracle Publishers that have previously been configured to use the server against which the wizard is running as their Distributor.</span></span> <span data-ttu-id="d3589-114">Если этот список пуст или нужный издатель Oracle в нем отсутствует, щелкните **Добавить издатель Oracle**.</span><span class="sxs-lookup"><span data-stu-id="d3589-114">If the list is empty, or the Oracle Publisher you want to use is not in the list, click **Add Oracle Publisher**.</span></span>  
  
 <span data-ttu-id="d3589-115">**Добавить издатель Oracle**</span><span class="sxs-lookup"><span data-stu-id="d3589-115">**Add Oracle Publisher**</span></span>  
 <span data-ttu-id="d3589-116">Щелкните для запуска диалогового окна **Свойства распространителя** .</span><span class="sxs-lookup"><span data-stu-id="d3589-116">Click to launch the **Distributor Properties** dialog box.</span></span> <span data-ttu-id="d3589-117">В этом диалоговом окне щелкните **Добавить**, затем — **Добавить издатель Oracle**.</span><span class="sxs-lookup"><span data-stu-id="d3589-117">In this dialog box, click **Add**, and then click **Add Oracle Publisher**.</span></span> <span data-ttu-id="d3589-118">В диалоговом окне **Соединение с сервером** укажите имя сервера Oracle, имя входа и пароль для схемы администраторской учетной записи репликации.</span><span class="sxs-lookup"><span data-stu-id="d3589-118">In the **Connect to Server** dialog box, specify the Oracle server name, and the login and password for the replication administrative user schema.</span></span> <span data-ttu-id="d3589-119">Дополнительные сведения см. в статье [Соединение с сервером (Oracle)](connect-to-server-oracle-login.md).</span><span class="sxs-lookup"><span data-stu-id="d3589-119">For more information, see [Connect to Server &#40;Oracle&#41;, Login](connect-to-server-oracle-login.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d3589-120">Если сервер, к которому обращается этот мастер, еще не настроен как распространитель, выдается запрос на его настройку.</span><span class="sxs-lookup"><span data-stu-id="d3589-120">If the server against which the wizard is running has not yet been configured as a Distributor, you are prompted to configure it now.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3589-121">См. также:</span><span class="sxs-lookup"><span data-stu-id="d3589-121">See Also</span></span>  
 [<span data-ttu-id="d3589-122">Создание публикации из базы данных Oracle</span><span class="sxs-lookup"><span data-stu-id="d3589-122">Create a Publication from an Oracle Database</span></span>](publish/create-a-publication-from-an-oracle-database.md)   

  
  
