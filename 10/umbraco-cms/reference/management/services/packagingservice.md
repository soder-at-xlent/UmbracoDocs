# PackagingService

The PackagingService provides import/export functionality for the Core models of the API.

* **Namespace:** `Umbraco.Core.Services`
* **Assembly:** `Umbraco.Core.dll`

All samples in this document will require references to the following dll:

* Umbraco.Core.dll

All samples in this document will require the following using statements:

```csharp
using Umbraco.Core;
using Umbraco.Core.Models;
using Umbraco.Core.Services;
```

## Getting the service

### Services property

If you wish to use use the packaging service in a class that inherits from one of the Umbraco base classes (eg. `SurfaceController`, `UmbracoApiController` or `UmbracoAuthorizedApiController`), you can access the packaging service through a local `Services` property:

```csharp
IPackagingService packagingService = Services.PackagingService;
```

### Dependency Injection

In other cases, you may be able to use Dependency Injection. For instance if you have registered your own class in Umbraco's dependency injection, you can specify the `IPackagingService` interface in your constructor:

```csharp
public class MyClass
{

    private IPackagingService _packagingService;

	public MyClass(IPackagingService packagingService)
	{
		_packagingService = packagingService;
	}

}
```

### Static accessor

If neither a `Services` property or Dependency Injection is available, you can also reference the static `Current` class directly:

```csharp
IPackagingService packagingService = Umbraco.Core.Composing.Current.Services.PackagingService;
```
