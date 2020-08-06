---
title: Сведения о заголовке и версии LocalDB SQL Server Express | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
api_location:
- sqluserinstance.dll
ms.assetid: 506b5161-b902-4894-b87b-9192d7b1664a
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 138081852cf505b03265fd9c5f39eae6ed2af39b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87668342"
---
# <a name="sql-server-express-localdb-header-and-version-information"></a><span data-ttu-id="e83dc-102">Заголовок и сведения о версии SQL Server Express LocalDB</span><span class="sxs-lookup"><span data-stu-id="e83dc-102">SQL Server Express LocalDB Header and Version Information</span></span>
  <span data-ttu-id="e83dc-103">Отдельный файл заголовка для интерфейса API экземпляра SQL Server Express LocalDB отсутствует. Сигнатуры функций LocalDB и коды ошибок определяются в файле заголовка собственного клиента SQL Server (sqlncli.h).</span><span class="sxs-lookup"><span data-stu-id="e83dc-103">There is no separate header file for the SQL Server Express LocalDB instance API; the LocalDB function signatures and error codes are defined in the SQL Server Native Client header file (sqlncli.h).</span></span> <span data-ttu-id="e83dc-104">Для использования интерфейса API экземпляра LocalDB необходимо включить в проект файл заголовка sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="e83dc-104">To use the LocalDB instance API, you must include the sqlncli.h header file in your project.</span></span>  
  
## <a name="localdb-versioning"></a><span data-ttu-id="e83dc-105">Управление версиями LocalDB</span><span class="sxs-lookup"><span data-stu-id="e83dc-105">LocalDB Versioning</span></span>  
 <span data-ttu-id="e83dc-106">Установка LocalDB использует по одному набору двоичных файлов на каждую из основных версий SQL Server.</span><span class="sxs-lookup"><span data-stu-id="e83dc-106">The LocalDB installation uses a single set of binaries per major SQL Server version.</span></span> <span data-ttu-id="e83dc-107">Эти версии LocalDB поддерживаются независимо. Исправления в них также вносятся независимо друг от друга.</span><span class="sxs-lookup"><span data-stu-id="e83dc-107">These LocalDB versions are maintained and patched independently.</span></span> <span data-ttu-id="e83dc-108">Это значит, что пользователю необходимо указывать используемый базовый выпуск LocalDB (то есть номер основной версии SQL Server).</span><span class="sxs-lookup"><span data-stu-id="e83dc-108">This means that the user has to specify which LocalDB baseline release (that is, major SQL Server version) he or she will be using.</span></span> <span data-ttu-id="e83dc-109">Версия указывается в стандартном формате версии, определяемом классом .NET Framework **System. Version** :</span><span class="sxs-lookup"><span data-stu-id="e83dc-109">The version is specified in the standard version format defined by the .NET Framework **System.Version** class:</span></span>  
  
 <span data-ttu-id="e83dc-110">*Major. minor [. Build [. Редакция]]*</span><span class="sxs-lookup"><span data-stu-id="e83dc-110">*major.minor[.build[.revision]]*</span></span>  
  
 <span data-ttu-id="e83dc-111">Первые два числа в строке версии (*основной* и *дополнительный*) являются обязательными.</span><span class="sxs-lookup"><span data-stu-id="e83dc-111">The first two numbers in the version string (*major* and *minor*) are mandatory.</span></span> <span data-ttu-id="e83dc-112">Последние два числа в строке версии (*Сборка* и *Редакция*) являются необязательными и по умолчанию равны нулю, если пользователь оставит их. Это означает, что если пользователь указывает в качестве номера версии LocalDB только "12,2", он будет рассматриваться так, как если бы пользователь указал "12.2.0.0".</span><span class="sxs-lookup"><span data-stu-id="e83dc-112">The last two numbers in the version string (*build* and *revision*) are optional and default to zero if the user leaves them out. This means that if the user specifies only "12.2" as the LocalDB version number, it will be treated as if the user specified "12.2.0.0".</span></span>  
  
 <span data-ttu-id="e83dc-113">Версия установки LocalDB определяется в разделе реестра MSSQLServer\CurrentVersion, который содержится в разделе реестра экземпляра SQL Server:</span><span class="sxs-lookup"><span data-stu-id="e83dc-113">The version for the LocalDB installation is defined in the MSSQLServer\CurrentVersion registry key under the SQL Server instance registry key, for example:</span></span>  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\MSSQL12E.LOCALDB\ MSSQLServer\CurrentVersion: "CurrentVersion"="12.0.2531.0"  
```  
  
 <span data-ttu-id="e83dc-114">Поддерживается параллельная работа нескольких версий LocalDB на одной рабочей станции.</span><span class="sxs-lookup"><span data-stu-id="e83dc-114">Multiple LocalDB versions on the same workstation are supported side-by-side.</span></span> <span data-ttu-id="e83dc-115">Однако пользовательский код всегда использует последнюю доступную библиотеку библиотеки **SQLUserInstance** на локальном компьютере для подключения к экземплярам LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e83dc-115">However, user code always uses the latest available **SQLUserInstance** DLL on the local computer to connect to LocalDB instances.</span></span>  
  
## <a name="locating-the-sqluserinstance-dll"></a><span data-ttu-id="e83dc-116">Поиск DLL-библиотеки SQLUserInstance</span><span class="sxs-lookup"><span data-stu-id="e83dc-116">Locating the SQLUserInstance DLL</span></span>  
 <span data-ttu-id="e83dc-117">Для размещения библиотеки DLL **SQLUserInstance** поставщик клиента использует следующий раздел реестра:</span><span class="sxs-lookup"><span data-stu-id="e83dc-117">To locate the **SQLUserInstance** DLL, the client provider uses the following registry key:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions]  
```  
  
 <span data-ttu-id="e83dc-118">Этот ключ содержит список ключей, по одному для каждой из установленных на компьютере версий LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e83dc-118">Under this key there is a list of keys, one for each version of LocalDB installed on the computer.</span></span> <span data-ttu-id="e83dc-119">Каждый из этих ключей именуется номером версии LocalDB в формате *\<major-version>* .*\<minor-version>*</span><span class="sxs-lookup"><span data-stu-id="e83dc-119">Each of these keys is named with the LocalDB version number in the format *\<major-version>*.*\<minor-version>*</span></span> <span data-ttu-id="e83dc-120">(например, ключ для [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] имеет имя 12,0).</span><span class="sxs-lookup"><span data-stu-id="e83dc-120">(for example, the key for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)] is named 12.0).</span></span> <span data-ttu-id="e83dc-121">В каждом из ключей версий содержится пара «имя-значение» `InstanceAPIPath`, определяющая полный путь к установленному в составе соответствующей версии файлу SQLUserInstance.dll.</span><span class="sxs-lookup"><span data-stu-id="e83dc-121">Under each version key there is an `InstanceAPIPath` name-value pair that defines the full path to the SQLUserInstance.dll file installed with that version.</span></span> <span data-ttu-id="e83dc-122">В следующем примере показаны записи реестра на компьютере, на котором установлены версии 11.0 и 12.0 LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e83dc-122">The following example shows the registry entries for a computer that has LocalDB versions 11.0 and 12.0 installed:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
```  
  
 <span data-ttu-id="e83dc-123">Поставщик клиента должен найти последнюю версию всех установленных версий и загрузить DLL-файл **SQLUserInstance** из связанного `InstanceAPIPath` значения.</span><span class="sxs-lookup"><span data-stu-id="e83dc-123">The client provider must find the latest version among all installed versions and load the **SQLUserInstance** DLL file from the associated `InstanceAPIPath` value.</span></span>  
  
### <a name="wow64-mode-on-64-bit-windows"></a><span data-ttu-id="e83dc-124">Режим WOW64 в 64-разрядной системе Windows</span><span class="sxs-lookup"><span data-stu-id="e83dc-124">WOW64 Mode on 64-bit Windows</span></span>  
 <span data-ttu-id="e83dc-125">У 64-разрядных установок LocalDB имеется дополнительный набор разделов реестра, который позволяет 32-разрядным приложениям, выполняющимся в режиме Windows-32-в-Windows-64 (WOW64), использовать LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e83dc-125">64-bit installations of LocalDB will have an additional set of registry keys to allow 32-bit applications running in Windows-32-on-Windows-64 (WOW64) mode to use LocalDB.</span></span> <span data-ttu-id="e83dc-126">Точнее говоря, в 64-разрядной Windows установщик MSI LocalDB создает следующие разделы реестра:</span><span class="sxs-lookup"><span data-stu-id="e83dc-126">Specifically, on 64-bit Windows, the LocalDB MSI will create the following registry keys:</span></span>  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Wow6432Node\Microsoft SQL Server Local DB\Installed Versions\12.0]  
"InstanceAPIPath"="C:\\Program Files (x86)\\Microsoft SQL Server\\120\\LocalDB\\Binn\\SqlUserInstance.dll"]  
  
```  
  
 <span data-ttu-id="e83dc-127">64-разрядные программы, считывающие ключ, увидят `Installed Versions` значения, указывающие на 64-разрядные версии библиотеки **SQLUserInstance** DLL, а 32-разрядные программы (работающие в 64-разрядных Windows в режиме WOW64) будут автоматически перенаправлены в `Installed Versions` раздел, расположенный в `Wow6432Node` кусте Hive.</span><span class="sxs-lookup"><span data-stu-id="e83dc-127">64-bit programs reading the `Installed Versions` key will see values pointing to 64-bit versions of the **SQLUserInstance** DLL, while 32-bit programs (running on 64-bit Windows in WOW64 mode) will be automatically redirected to an `Installed Versions` key located under the `Wow6432Node` hive.</span></span> <span data-ttu-id="e83dc-128">Этот ключ содержит значения, указывающие на 32-разрядные версии библиотеки **SQLUserInstance** .</span><span class="sxs-lookup"><span data-stu-id="e83dc-128">This key contains values pointing to 32-bit versions of the **SQLUserInstance** DLL.</span></span>  
  
## <a name="using-localdb_define_proxy_functions"></a><span data-ttu-id="e83dc-129">Использование константы LOCALDB_DEFINE_PROXY_FUNCTIONS</span><span class="sxs-lookup"><span data-stu-id="e83dc-129">Using LOCALDB_DEFINE_PROXY_FUNCTIONS</span></span>  
 <span data-ttu-id="e83dc-130">API экземпляра LocalDB определяет константу с именем LOCALDB_DEFINE_PROXY_FUNCTIONS, которая автоматизирует обнаружение и загрузку библиотеки **SQLUserInstance** DLL.</span><span class="sxs-lookup"><span data-stu-id="e83dc-130">The LocalDB instance API defines a constant named LOCALDB_DEFINE_PROXY_FUNCTIONS that automates the discovery and loading of the **SqlUserInstance** DLL.</span></span>  
  
 <span data-ttu-id="e83dc-131">Раздел кода, включаемый этой константой, содержит реализацию учетных записей-посредников для каждого из интерфейсов API LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e83dc-131">The section of code enabled by this constant provides an implementation of proxies for each of the LocalDB APIs.</span></span> <span data-ttu-id="e83dc-132">Реализации прокси-сервера используют общую функцию для привязки к точкам входа в последней установленной библиотеке **SQLUserInstance** DLL, а затем перенаправляют запросы.</span><span class="sxs-lookup"><span data-stu-id="e83dc-132">The proxy implementations use a common function to bind to entry points in the latest installed **SqlUserInstance** DLL, and then forward the requests.</span></span>  
  
 <span data-ttu-id="e83dc-133">Функции учетной записи-посредника включаются лишь в случае, если константа LOCALDB_DEFINE_PROXY_FUNCTIONS определяется в пользовательском коде перед включением файла sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="e83dc-133">The proxy functions are enabled only if the constant LOCALDB_DEFINE_PROXY_FUNCTIONS is defined in the user code before including the sqlncli.h file.</span></span> <span data-ttu-id="e83dc-134">Эту константу следует определять только в одном исходном модуле (CPP-файле), так как она определяет внешние имена функций для всех точек входа интерфейса API.</span><span class="sxs-lookup"><span data-stu-id="e83dc-134">The constant should be defined in only one source module (.cpp file) because it defines external function names for all of the API entry points.</span></span> <span data-ttu-id="e83dc-135">Она предоставляет реализацию прокси-классов для каждого из API-интерфейсов LocalDB.</span><span class="sxs-lookup"><span data-stu-id="e83dc-135">It provides an implementation of proxies for each of the LocalDB APIs.</span></span>  
  
 <span data-ttu-id="e83dc-136">В следующем примере кода показано использование макроса из собственного кода C++:</span><span class="sxs-lookup"><span data-stu-id="e83dc-136">The following code example shows how to use the macro from the native C++ code:</span></span>  
  
```  
// Define the LOCALDB_DEFINE_PROXY_FUNCTIONS constant to enable the LocalDB proxy functions   
// The #define has to take place BEFORE the API header file (sqlncli.h) is included  
#define LOCALDB_DEFINE_PROXY_FUNCTIONS  
#include <sqlncli.h>  
...  
HRESULT hr = S_OK;  
  
// Create LocalDB instance by calling the create API proxy function included by macro  
if (FAILED(hr = LocalDBCreateInstance( L"12.0", L"name", 0)))  
{  
...  
}  
...  
  
```  
  
  
