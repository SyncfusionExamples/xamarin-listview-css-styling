# How to style Xamarin.Forms ListView using Cascading Style Sheet(CSS) 

You can style visual elements in ItemTemplate of Xamarin.Forms ListView using cascading style sheet. This KB article explains the usage of stylesheets. 

## Create CSS on Xamarin.Forms apps

1.	Create a empty stylesheet.css file by right-clicking your .Net standard library project.
2.	Set the build action of CSS file to EmbeddedResource.
  
## Consuming a Style sheet

3.	Define your ContentPage elements using Selectors for styling like below.

```
<ContentPage>
        <Grid>
            <Grid.RowDefinitions>
                <RowDefinition Height="*"/>
            </Grid.RowDefinitions>
            <sync:SfListView  AutoFitMode="Height" x:Name="listView"
                   ItemsSource="{Binding BookInfo}">
                <sync:SfListView.ItemTemplate>
                    <DataTemplate>
                        <Grid Padding="10">
                            <Grid.RowDefinitions>
                                <RowDefinition Height="0.4*" />
                                <RowDefinition Height="0.6*" />
                            </Grid.RowDefinitions>
                            <Label x:Name="label" Text="{Binding BookName}" StyleClass="bookName" />
                        <Label Grid.Row="1" Text="{Binding BookDescription}" StyleClass="bookDescription" />
                        </Grid>
                    </DataTemplate>
                </sync:SfListView.ItemTemplate>
            </sync:SfListView>
        </Grid>
</ContentPage>
```

4.	Apply style to the ContentPage elements in your CSS like below.

```
#listView 
{
    background-color: lightgray;
}
grid 
{
    margin: 20;
}
.bookName 
{
    font-style: bold;
    font-size: medium;
}
.bookDescription 
{
    margin-top: 15;
}
```

## Loading a style sheet

5.	A style sheet can be loaded and parsed with the StyleSheet class before being added to a ResourceDictionary.
 
```
<Application>
    <Application.Resources>
        <StyleSheet Source="/Assets/styles.css" />
    </Application.Resources>
</Application>
```
 For more reference, please refer [Xamarin.forms CSS](https://docs.microsoft.com/en-us/xamarin/xamarin-forms/user-interface/styles/css/) Documentation.