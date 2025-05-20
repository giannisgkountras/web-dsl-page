Screens are used to define the layout of the application. They are defined using the following syntax:

```
Screen ScreenName
    description: "Description of the screen"
    title: "Title of the screen"
    url: "/home"


end
```

-   **description**: The description of the screen.
-   **title**: The title of the screen also used in the navbar.
-   **url**: The url of the screen. This is used to navigate to the screen.

Each screen can contain rows and columns to define the layout, links to other screens or external urls, components, conditions and loops.
The syntax for defining a row is:

```
row
endrow

```

The syntax for defining a column is:

```
col
endcol
```

The syntax for defining a link is:

```
link
    url: "/home"
    text: "Home"
end
```

The syntax for using a component is:

```
use ComponentName
```

or you can define it inline.

A complete example of a screen is:

```
Screen Home
    description: "Home screen"
    title: "Home"
    url: "/home"
    row
        col
            use MyComponent1
        endcol
        col
            Component Title
                type: Text content: "Hello World"
            end
        endcol
    endrow
end
```
