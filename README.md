# access-listview-inside-data-template-in-.net-maui

This example demonstrates how to access the SfListView element inside DataTemplate .NET MAUI Platform.

## Sample

```xaml
<popup:SfPopup x:Name="popupLayout" WidthRequest="350" HeightRequest="350">
    <popup:SfPopup.ContentTemplate>
        <DataTemplate>
            <Grid>
                <Grid.Behaviors>
                    <local:GridBehavior/>
                </Grid.Behaviors>
                <Grid.RowDefinitions>

                    <RowDefinition Height="50"/>
                    <RowDefinition Height="*"/>
                </Grid.RowDefinitions>

                <Button Text="Find ListView" x:Name="listviewButton" BackgroundColor="LightGray"/>
                <sfListView:SfListView    x:Name="listView"  ItemSpacing="5" 
                ItemsSource="{Binding Items}" 
                SelectionMode="Single" Grid.Row="1">
                    <sfListView:SfListView.ItemTemplate>
                        <DataTemplate>
                            <Grid x:Name="grid" RowSpacing="1">
                                <Grid.RowDefinitions>
                                    <RowDefinition Height="*" />
                                </Grid.RowDefinitions>
                                <Grid.ColumnDefinitions>
                                    <ColumnDefinition Width="50" />
                                    <ColumnDefinition Width="*" />
                                </Grid.ColumnDefinitions>

                                <Image Source="{Binding ContactImage}"
                VerticalOptions="Center"
                HorizontalOptions="Center"
                HeightRequest="50"/>

                                <Label  Grid.Column="1"
                HorizontalTextAlignment="Center"
                HorizontalOptions="StartAndExpand"
                LineBreakMode="NoWrap"
                Text="{Binding ContactName}" 
                FontSize="Medium" />

                            </Grid>
                        </DataTemplate>
                    </sfListView:SfListView.ItemTemplate>
                </sfListView:SfListView>
            </Grid>
        </DataTemplate>
    </popup:SfPopup.ContentTemplate>
</popup:SfPopup>
```

## Requirements to run the demo

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## Troubleshooting

### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

