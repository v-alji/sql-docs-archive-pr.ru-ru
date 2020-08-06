---
title: Шаг 2. Проверка пакета развертывания | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 6c13f5c9-c75e-4e52-94dc-2d2db2c578fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: f452a87154175ac05a050761d8f12b6bfe61cd8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87655829"
---
# <a name="step-2-verifying-the-deployment-bundle"></a><span data-ttu-id="9676b-102">Этап 2. Проверка пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="9676b-102">Step 2: Verifying the Deployment Bundle</span></span>
  <span data-ttu-id="9676b-103">На занятии 1 был создан проект учебного развертывания и в него добавлены пакеты и вспомогательные файлы; в предыдущей задаче была построена программа развертывания для проекта.</span><span class="sxs-lookup"><span data-stu-id="9676b-103">In lesson 1, you created the Deployment Tutorial project and added packages and ancillary files to the project; in the previous task you built a deployment utility for the project.</span></span>  
  
 <span data-ttu-id="9676b-104">В этой задаче будет проверено содержимое пакета развертывания.</span><span class="sxs-lookup"><span data-stu-id="9676b-104">In this task, you will verify the contents of the deployment bundle.</span></span> <span data-ttu-id="9676b-105">Пакет развертывания представляет собой папку, которая будет скопирована на целевой компьютер и использована для установки пакетов.</span><span class="sxs-lookup"><span data-stu-id="9676b-105">The deployment bundle is the folder that you will copy to the destination computer and use to install packages.</span></span> <span data-ttu-id="9676b-106">Если в качестве местонахождения для программы развертывания было использовано значение по умолчанию bin\Deployment, пакетом развертывания будет папка Bin\Deployment в папке Deployment Tutorial в проекте [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9676b-106">If you used the default value-bin\Deployment-as the location of the deployment utility, the deployment bundle is the Bin\Deployment folder within the Deployment Tutorial folder in the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project.</span></span>  
  
### <a name="to-verify-the-content-of-deployment-bundle"></a><span data-ttu-id="9676b-107">Проверка содержимого пакета развертывания</span><span class="sxs-lookup"><span data-stu-id="9676b-107">To verify the content of deployment bundle</span></span>  
  
1.  <span data-ttu-id="9676b-108">Выберите папку bin\Deployment.</span><span class="sxs-lookup"><span data-stu-id="9676b-108">Locate the bin\Deployment folder on your computer.</span></span>  
  
2.  <span data-ttu-id="9676b-109">Проверьте наличие в папке следующих файлов:</span><span class="sxs-lookup"><span data-stu-id="9676b-109">Verify that the following files are present:</span></span>  
  
    -   <span data-ttu-id="9676b-110">DataTransfer.dtsx</span><span class="sxs-lookup"><span data-stu-id="9676b-110">DataTransfer.dtsx</span></span>  
  
    -   <span data-ttu-id="9676b-111">datatransferconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="9676b-111">datatransferconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="9676b-112">Deployment Tutorial.SSISDeploymentManifest</span><span class="sxs-lookup"><span data-stu-id="9676b-112">Deployment Tutorial.SSISDeploymentManifest</span></span>  
  
    -   <span data-ttu-id="9676b-113">LoadXMLData.dtsx</span><span class="sxs-lookup"><span data-stu-id="9676b-113">LoadXMLData.dtsx</span></span>  
  
    -   <span data-ttu-id="9676b-114">loadxmldataconfig.dtsconfig</span><span class="sxs-lookup"><span data-stu-id="9676b-114">loadxmldataconfig.dtsconfig</span></span>  
  
    -   <span data-ttu-id="9676b-115">NewCustomers.txt</span><span class="sxs-lookup"><span data-stu-id="9676b-115">NewCustomers.txt</span></span>  
  
    -   <span data-ttu-id="9676b-116">orders.xml</span><span class="sxs-lookup"><span data-stu-id="9676b-116">orders.xml</span></span>  
  
    -   <span data-ttu-id="9676b-117">orders.xsd</span><span class="sxs-lookup"><span data-stu-id="9676b-117">orders.xsd</span></span>  
  
    -   <span data-ttu-id="9676b-118">Readme.txt</span><span class="sxs-lookup"><span data-stu-id="9676b-118">Readme.txt</span></span>  
  
3.  <span data-ttu-id="9676b-119">Щелкните правой кнопкой файл Deployment Tutorial.SSISDeploymentManifest, наведите указатель на пункт **Открыть с помощью**и выберите пункт **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9676b-119">Right-click Deployment Tutorial.SSISDeploymentManifest, point **to Open With**, and then click **Internet Explorer**.</span></span> <span data-ttu-id="9676b-120">Файл также можно открыть в текстовом редакторе, например в приложении «Блокнот».</span><span class="sxs-lookup"><span data-stu-id="9676b-120">You can also open the file in a text editor such as Notepad.</span></span> <span data-ttu-id="9676b-121">Код XML в файле должен быть таким:</span><span class="sxs-lookup"><span data-stu-id="9676b-121">The XML code of the file should be the following:</span></span>  
  
     `<?xml version="1.0"?><DTSDeploymentManifest GeneratedBy="Domain\UserName" GeneratedFromProjectName="Deployment Tutorial" GeneratedDate="2006-02-24T13:29:02.6537669-08:00" AllowConfigurationChanges="true"><Package>DataTransfer.dtsx</Package><Package>LoadXMLData.dtsx</Package><ConfigurationFile>datatransferconfig.dtsconfig</ConfigurationFile><ConfigurationFile>loadxmldataconfig.dtsconfig</ConfigurationFile><MiscellaneousFile>Readme.txt</MiscellaneousFile><MiscellaneousFile>orders.xml</MiscellaneousFile><MiscellaneousFile>NewCustomers.txt</MiscellaneousFile><MiscellaneousFile>orders.xsd</MiscellaneousFile></DTSDeploymentManifest>`  
  
4.  <span data-ttu-id="9676b-122">Убедитесь, что значение `AllowConfigurationChanges` атрибута равно **true** , а XML включает `Package` элемент для каждого из этих двух пакетов, `MiscellaneousFile` элемент для каждого из четырех файлов, не являющихся пакетами, и `ConfigurationFile` элемент для каждого из двух XML-файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9676b-122">Verify that the value of the `AllowConfigurationChanges` attribute is **true** and the XML includes a `Package` element for each of the two packages, a `MiscellaneousFile` element for each of the four non-package files, and a `ConfigurationFile` element for each of the two XML configuration files.</span></span>  
  
5.  <span data-ttu-id="9676b-123">Закройте обозреватель Internet Explorer или текстовый редактор.</span><span class="sxs-lookup"><span data-stu-id="9676b-123">Exit Internet Explorer or the text editor.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="9676b-124">Следующее занятие</span><span class="sxs-lookup"><span data-stu-id="9676b-124">Next Lesson</span></span>  
 [<span data-ttu-id="9676b-125">Занятие 3. Установка пакетов</span><span class="sxs-lookup"><span data-stu-id="9676b-125">Lesson 3: Installing Packages</span></span>](../integration-services/lesson-3-install-ssis-package.md)  
  
<span data-ttu-id="9676b-126">![Значок Integration Services (маленький)](media/dts-16.gif "Значок служб Integration Services (маленький)")  **следит за обновлениями Integration Services**</span><span class="sxs-lookup"><span data-stu-id="9676b-126">![Integration Services icon (small)](media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="9676b-127">Чтобы загрузить новейшую документацию, статьи, образцы и видеоматериалы корпорации Майкрософт, а также лучшие решения участников сообщества, посетите страницу служб [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] на сайте MSDN:</span><span class="sxs-lookup"><span data-stu-id="9676b-127">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="9676b-128">Посетить страницу «Службы Integration Services» на сайте MSDN</span><span class="sxs-lookup"><span data-stu-id="9676b-128">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="9676b-129">Чтобы получать автоматические уведомления об этих обновлениях, подпишитесь на RSS-каналы, предлагаемые на этой странице.</span><span class="sxs-lookup"><span data-stu-id="9676b-129">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
