# IRecipeManager

Default interface for Registry based handlers as they can all remove recipes by ResourceLocation.

## Diese Klasse importieren

It might be required for you to import the package if you encounter any issues (like casting an Array), so better be safe than sorry and add the import at the very top of the file.
```zenscript
import crafttweaker.api.registries.IRecipeManager;
```


## Implemented Interfaces
IRecipeManager implements the following interfaces. That means all methods defined in these interfaces are also available in IRecipeManager

- [CommandStringDisplayable](/vanilla/api/brackets/CommandStringDisplayable)

## Methoden

### addJSONRecipe

Adds a recipe based on a provided IData. The provided IData should represent a DataPack JSON, this effectively allows you to register recipes for any DataPack supporting IRecipeType systems.

Return Type: void

```zenscript
IRecipeManager.addJSONRecipe(name as string, data as IData) as void
craftingTable.addJSONRecipe("recipe_name", {ingredient:{item:<item:minecraft:gold_ore>.registryName},result:<item:minecraft:cooked_porkchop>.registryName,experience:0.35 as float, cookingtime:100});
```

| Parameter | Type                             | Beschreibung                    |
| --------- | -------------------------------- | ------------------------------- |
| name      | string                           | name of the recipe              |
| data      | [IData](/vanilla/api/data/IData) | data representing the json file |


### getAllRecipes

Return Type: stdlib.List&lt;[WrapperRecipe](/vanilla/api/recipe/WrapperRecipe)&gt;

```zenscript
IRecipeManager.getAllRecipes() as stdlib.List<WrapperRecipe>
craftingTable.getAllRecipes();
```

### getRecipeByName

Return Type: [WrapperRecipe](/vanilla/api/recipe/WrapperRecipe)

```zenscript
IRecipeManager.getRecipeByName(name as string) as WrapperRecipe
```

| Parameter | Type   | Beschreibung            |
| --------- | ------ | ----------------------- |
| name      | string | No Description Provided |


### getRecipesByAusgabe

Return Type: stdlib.List&lt;[WrapperRecipe](/vanilla/api/recipe/WrapperRecipe)&gt;

```zenscript
IRecipeManager.getRecipesByOutput(output as IIngredient) as stdlib.List<WrapperRecipe>
```

| Parameter | Type                                          | Beschreibung            |
| --------- | --------------------------------------------- | ----------------------- |
| output    | [IIngredient](/vanilla/api/items/IIngredient) | No Description Provided |


### removeAll

Remove all recipes in this registry

Return Type: void

```zenscript
IRecipeManager.removeAll() as void
craftingTable.removeAll();
```

### removeByModid

Remove recipe based on Registry name modid

Return Type: void

```zenscript
IRecipeManager.removeByModid(modid as string) as void
craftingTable.removeByModid("minecraft");
```

| Parameter | Type   | Beschreibung                   |
| --------- | ------ | ------------------------------ |
| modid     | string | modid of the recipes to remove |


Remove recipe based on Registry name modid with an added exclusion check, so you can remove the whole mod besides a few specified.

Return Type: void

```zenscript
IRecipeManager.removeByModid(modid as string, exclude as RecipeFilter) as void
craftingTable.removeByModid("minecraft", (name as string) => {return name == "orange_wool";});
```

| Parameter    | Type                                             | Beschreibung                   |
| ------------ | ------------------------------------------------ | ------------------------------ |
| modid        | string                                           | modid of the recipes to remove |
| ausschließen | [RecipeFilter](/vanilla/api/recipe/RecipeFilter) | zu entfernende Rezepte.        |


### removeByName

Remove recipe based on Registry name

Return Type: void

```zenscript
IRecipeManager.removeByName(name as string) as void
craftingTable.removeByName("minecraft:furnace");
```

| Parameter | Type   | Beschreibung                      |
| --------- | ------ | --------------------------------- |
| name      | string | registry name of recipe to remove |


### removeByRegex

Remove recipe based on regex

Return Type: void

```zenscript
IRecipeManager.removeByRegex(regex as string) as void
craftingTable.removeByRegex("\\d_\\d");
```

| Parameter | Type   | Beschreibung           |
| --------- | ------ | ---------------------- |
| regex     | string | regex to match against |


### removeRecipe

Remove a recipe based on it's output.

Return Type: void

```zenscript
IRecipeManager.removeRecipe(output as IItemStack) as void
craftingTable.removeRecipe(<item:minecraft:glass>);
```

| Parameter | Type                                        | Beschreibung         |
| --------- | ------------------------------------------- | -------------------- |
| output    | [IItemStack](/vanilla/api/items/IItemStack) | output of the recipe |



