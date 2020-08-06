---
title: Установка распределенное воспроизведение с помощью файла конфигурации | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 3259232c-6963-4c9c-9d10-ae42aa262eef
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7757cce29c2e6b3ce4f1e91fc97cbf8be02ae521
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87735897"
---
# <a name="install-distributed-replay-using-a-configuration-file"></a><span data-ttu-id="df2e7-102">Установка компонентов распределенного воспроизведения с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="df2e7-102">Install Distributed Replay Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="df2e7-103">дает возможность создать файл конфигурации на основе данных пользователя и значений системы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="df2e7-103">Setup provides the ability to generate a configuration file based on user input and system defaults.</span></span> <span data-ttu-id="df2e7-104">Если необходимо установить средства управления, можно использовать файл конфигурации для развертывания трех компонентов распределенного воспроизведения (средство администрирования, контроллер распределенного воспроизведения и клиент распределенного воспроизведения).</span><span class="sxs-lookup"><span data-stu-id="df2e7-104">If you specify that you want the Management tools installed, you can use the configuration file to deploy the three Distributed Replay components (administration tool, Distributed Replay controller, and the Distributed Replay client).</span></span> <span data-ttu-id="df2e7-105">Поддерживает установку, восстановление и удаление компонентов распределенного воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="df2e7-105">It supports Installing, repairing, and uninstalling of the Distributed Replay components.</span></span>  
  
 <span data-ttu-id="df2e7-106">Программа установки поддерживает использование файлов конфигурации только через командную строку.</span><span class="sxs-lookup"><span data-stu-id="df2e7-106">Setup supports the use of the configuration file only through the command-line.</span></span> <span data-ttu-id="df2e7-107">Порядок обработки параметров при использовании файла конфигурации описывается ниже.</span><span class="sxs-lookup"><span data-stu-id="df2e7-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="df2e7-108">Файл конфигурации перезаписывает значения по умолчанию в пакете.</span><span class="sxs-lookup"><span data-stu-id="df2e7-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="df2e7-109">Значения командной строки перезаписывают значения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="df2e7-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="df2e7-110">Дополнительные сведения об использовании файла конфигурации см. в разделе [Install SQL Server 2014 с помощью файла конфигурации](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="df2e7-110">For more information about how to use a configuration file, see [Install SQL Server 2014 Using a Configuration File](../../database-engine/install-windows/install-sql-server-using-a-configuration-file.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="df2e7-111">После установки компонентов распределенного воспроизведения необходимо создать правила брандмауэра на компьютерах контроллера и клиента и предоставить каждому из клиентских компьютеров разрешения на целевом сервере.</span><span class="sxs-lookup"><span data-stu-id="df2e7-111">After you install Distributed Replay you must create firewall rules on the controller and client computers, and grant each client computer permissions on the target server.</span></span> <span data-ttu-id="df2e7-112">Дополнительные сведения см. в статье [Выполнение действий после установки](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span><span class="sxs-lookup"><span data-stu-id="df2e7-112">For more information, see [Complete the Post-Installation Steps](../../tools/distributed-replay/complete-the-post-installation-steps.md).</span></span>  
  
### <a name="to-generate-a-configuration-file"></a><span data-ttu-id="df2e7-113">Создание файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="df2e7-113">To generate a configuration file</span></span>  
  
1.  <span data-ttu-id="df2e7-114">Следуйте указаниям мастера установки до страницы **Все готово для установки** .</span><span class="sxs-lookup"><span data-stu-id="df2e7-114">Follow the Setup wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="df2e7-115">Путь к файлу конфигурации указывается на странице **Все готово для установки** в разделе пути файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="df2e7-115">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span>  
  
2.  <span data-ttu-id="df2e7-116">Отмените установку, не завершая ее, чтобы создать INI-файл.</span><span class="sxs-lookup"><span data-stu-id="df2e7-116">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
### <a name="to-install-distributed-replay-using-the-configuration-file"></a><span data-ttu-id="df2e7-117">Установка компонентов распределенного воспроизведения с помощью файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="df2e7-117">To Install Distributed Replay Using the Configuration File</span></span>  
  
-   <span data-ttu-id="df2e7-118">Запустите установку из командной строки и укажите файл ConfigurationFile.ini в параметре ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="df2e7-118">Run the installation through the command prompt and supply the ConfigurationFile.ini using the ConfigurationFile parameter.</span></span>  
  
 <span data-ttu-id="df2e7-119">**Образец синтаксиса**</span><span class="sxs-lookup"><span data-stu-id="df2e7-119">**Sample Syntax**</span></span>  
  
 <span data-ttu-id="df2e7-120">Далее приведен пример указания файла конфигурации в командной строке.</span><span class="sxs-lookup"><span data-stu-id="df2e7-120">Following is an example on how to specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /CTLRSVCPASSWORD="ctlrsvcpswd" /CLTSVCPASSWORD="cltsvcpswd" / ConfigurationFile=ConfigurationFile.INI\  
```  
  
> [!NOTE]  
>  <span data-ttu-id="df2e7-121">Необходимо указать оба пароля в командной строке, так как их нельзя задать в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="df2e7-121">You must specify both passwords in the command line because you cannot configure them in the configuration file.</span></span>  
  
  
