# GraphQL Project

## Run


```bash
docker compose up --build
cd GraphQLProject/GraphQLProject
dotnet run
```

- open link `https://localhost:5006/graphql`

## Query

### GetAll

```graphql
query get{
    menus{
        id
        name
        price
        description
    }
}
```

### GetById

```graphql
query get{
    menu(menuId:5){
        id
        name
        price
        description
    }
}
```

### Add

```graphql
query add($menu: MenuInputType){
    CreateMenu(menu:$menu){
        id
        name
        price
        description
    }
}
```

- Query variables
  
```json
{
    "menu": {
        "id": 6,
        "name": "a",
        "description": "b",
        "price": 5.1
    }
}
```

### Update

```graphql
query UpdateMenu($menuId:Int $menu: MenuInputType){
    updateMenu(menuId:$menuId menu:$menu){
        id
        name
        price
        description
    }
}
```

- Query variables
  
```json
{
    "menuId":6,
    "menu": {
        "id": 6,
        "name": "a",
        "description": "b",
        "price": 2.1
    }
}
```

### Delete

```graphql
query DeleteMenu($menu: MenuInputType){
    deleteMenu(menuId:$menuId)
}
```

- Query variables
  
```json
{
    "menuId":6
}
```
