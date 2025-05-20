The language supports multi-file models via model imports.
A nested model import layer is implemented, enabling pythonic imports
of models defined in other files.

```
// webpage.wdsl

import "screens.wdsl"

Webpage MyWebpage
    author: ""
    version: "1.0"
    description: ""
    navbar: true

    API backendAPI
        host: "0.0.0.0"
        port: 8321
    end

    Websocket backendWebsocket
        host: "localhost"
        port: 8080
    end
```

```
// screens.wdsl
import "components.wdsl"

Screen Home
    title: "Home"
    url: "/"

    use InfoNotifications

    row
        col
            use ProductsTable
        endcol
        col
            use WarehousesTable
        endcol
    endrow
end
```

The model can be seperated into as many files as needed.
