---
title: Диспетчер подключений Azure Data Lake Store | Документы Майкрософт
ms.custom: ''
ms.date: 06/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- SQL12.DTS.DESIGNER.AFPADLSCM.F1
- SQL11.DTS.DESIGNER.AFPADLSCM.F1
ms.assetid: 7f1323f9-9dc3-4378-9c70-bbc65bfeabfd
author: yualan
ms.author: chugu
ms.openlocfilehash: 1ab6e90aad6472cc10bbb12cf4ca17def501bf00
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87740238"
---
# <a name="azure-data-lake-store-connection-manager"></a><span data-ttu-id="b6c3d-102">Диспетчер подключений Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="b6c3d-102">Azure Data Lake Store Connection Manager</span></span>
  <span data-ttu-id="b6c3d-103">**Диспетчер подключений Azure Data Lake Store** позволяет пакету служб SSIS подключаться к службе Azure Data Lake Store с помощью двух типов проверки подлинности: удостоверение пользователя Azure AD и удостоверение службы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-103">The **Azure Data Lake Store connection manager** enables an SSIS package to connect to an Azure Data Lake Store service through two authentication types: Azure AD User Identity and Azure AD Service Identity.</span></span>  

## <a name="configure-the-azure-data-lake-store-connection-manager"></a><span data-ttu-id="b6c3d-104">Настройка диспетчера подключений Azure Data Lake Store</span><span class="sxs-lookup"><span data-stu-id="b6c3d-104">Configure the Azure Data Lake Store Connection Manager</span></span> 
  
1.  <span data-ttu-id="b6c3d-105">В диалоговом окне **Добавление диспетчера соединений со службами SSIS** выберите **AzureDataLake**и щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-105">In the **Add SSIS Connection Manager** dialog box, select **AzureDataLake**, and click **Add**.</span></span>   
  
2.  <span data-ttu-id="b6c3d-106">В диалоговом окне "Редактор диспетчера подключений Azure Data Lake Store" введите URL-адрес узла Azure Data Lake Store в поле **Узел ADLS** .</span><span class="sxs-lookup"><span data-stu-id="b6c3d-106">In the Azure Data Lake Store Connection Manager Editor dialog box, type in the Azure Data Lake Store host URL in **ADLS Host** field.</span></span> <span data-ttu-id="b6c3d-107">Например: https: \/ /Test.azuredatalakestore.NET или Test.azuredatalakestore.NET.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-107">For example: https:\//test.azuredatalakestore.net or test.azuredatalakestore.net.</span></span>
  
3.  <span data-ttu-id="b6c3d-108">Выберите соответствующий тип проверки подлинности для доступа к данным Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-108">Choose corresponding authentication type to access Azure Data Lake Store data.</span></span>

    1.  <span data-ttu-id="b6c3d-109">Если вы выбрали вариант **удостоверение пользователя Azure AD** , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-109">If you selected **Azure AD User Identity** authentication option, do the following:</span></span>

        1. <span data-ttu-id="b6c3d-110">Укажите значения в полях **Имя пользователя** и **Пароль** .</span><span class="sxs-lookup"><span data-stu-id="b6c3d-110">Specify values for the **User Name** and **Password** field.</span></span> 
    
        2. <span data-ttu-id="b6c3d-111">Щелкните **Проверить подключение** для проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-111">Click **Test Connection** button to test the connection.</span></span> <span data-ttu-id="b6c3d-112">Если вы ранее не согласовали доступ служб SSIS к данным Azure Data Lake Store с администратором клиента, во всплывающем диалоговом окне нажмите кнопку **Принять** , чтобы разрешить службам SSIS доступ к данным Azure Data Lake Store.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-112">If you and your tenant administrator didn't consent SSIS to access your Azure Data Lake Store data before, you need click **Accept** button to consent SSIS to access your Azure Data Lake Store data in the pop out dialog.</span></span> <span data-ttu-id="b6c3d-113">Дополнительные сведения о предоставлении согласия см. в разделе [Интеграция приложений с Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="b6c3d-113">For more information about this consent experience, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration#integrating-applications-with-azure-ad).</span></span>
    
        > [!NOTE] 
        > <span data-ttu-id="b6c3d-114">При выборе параметра проверки подлинности "Удостоверение пользователя Azure AD" многофакторная проверка подлинности и учетная запись Майкрософт НЕ поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-114">For Azure AD User Identity authentication option, multi-factor authentication and Microsoft account is NOT supported.</span></span>
    
    2.  <span data-ttu-id="b6c3d-115">Если вы выбрали вариант **удостоверение службы Azure AD** , выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-115">If you selected **Azure AD Service Identity** authentication option, do the following:</span></span>
        1. <span data-ttu-id="b6c3d-116">Создайте приложение AAD и субъект-службу, которые могут получать доступ к ресурсам Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-116">Create an AAD application and service principal that can access Azure Data Lake resources.</span></span>
    
        2. <span data-ttu-id="b6c3d-117">Назначьте приложению AAD соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-117">Assign this AAD application corresponding permissions to access your Azure Data Lake resources.</span></span> <span data-ttu-id="b6c3d-118">Дополнительные сведения об этом параметре проверки подлинности см. в разделе [Использовать портал для создания приложения и службы-участника, который имеет доступ к ресурсам Active Directory](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span><span class="sxs-lookup"><span data-stu-id="b6c3d-118">For more information about this authentication option, see [Use portal to create Active Directory application and service principal that can access resources](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-create-service-principal-portal).</span></span>
    
        3. <span data-ttu-id="b6c3d-119">Укажите значения в полях **Идентификатор клиента**, **Секретный ключ** и **Имя клиента** .</span><span class="sxs-lookup"><span data-stu-id="b6c3d-119">Specify values for **Client Id**, **Secret Key** and **Tenant Name** field.</span></span>
    
        4. <span data-ttu-id="b6c3d-120">Щелкните **Проверить подключение** для проверки подключения.</span><span class="sxs-lookup"><span data-stu-id="b6c3d-120">Click **Test Connection** button to test the connection.</span></span>  
  
4.  <span data-ttu-id="b6c3d-121">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="b6c3d-121">Click **OK** to close the dialog box.</span></span>  
  
    <span data-ttu-id="b6c3d-122">Свойства созданного диспетчера соединений можно просмотреть в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="b6c3d-122">You can see the properties of the connection manager you created in the **Properties** window.</span></span>  
  
  
