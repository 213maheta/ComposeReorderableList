# ComposeReorderableList

### 1) Add in your gradle

```
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        **maven { url 'https://jitpack.io' }**
    }
}
```


### 2) Add in your app level build gradle
   ```
   implementation 'com.github.213maheta:ComposeReorderableList:1.0.1'
```


### 3) Add **reOrderableList** in your LazyColumn

```
LazyColumn(state = listState,
        modifier = Modifier
            .fillMaxWidth()
            .fillMaxHeight()
            **.reOrderableList(listState) { selected: Int, hover: Int ->
                pageNumberList.swap(selected, hover)
            }**
    ) {............
```


### 4) Add **.reOrderableItem(index)** in your list item
```
Row(
        modifier = Modifier
            .fillMaxWidth()
            **.reOrderableItem(index)**
            .padding(4.dp)
            .border(
                width = 2.dp,
                color = colorResource(id = R.color.orange),
                shape = RoundedCornerShape(10.dp)
            )
            .padding(10.dp)
    )
    {
```  

<div align="center">
  <video src="https://github.com/213maheta/ComposeReorderableList/assets/103872646/0e5850b4-b433-4f40-89e1-64494c7d0f9f" />
</div>
