# Fixtures

## Example

Say with have a simple ```Item``` class. We will want to configure this class different depending on certain test scenarios.

``` C#
public class Item {
    public int Id { get; set; }
    public decimal Price { get; set; }
    public string Name { get; set; }
    public DateTime ExpiryDate { get; set;}
}
```

To make our lives easier we can make a fixture builder class to easily help us configure different ```Item```s for testing.

``` C#
public class ItemFixture {
    private readonly Item _item;

    public const string DefaultItemId = "itemId";

    public ItemFixture()
    {
        _item = new Item()
        {
            Id = DefaultItemId;
        }
    }

    public ItemFixture WithPrice(decimal price)
    {
        _item.Price = price;
        return this;
    }

    public ItemFixture WithName(string name)
    {
        _item.Name = name;
        return this;
    }

    public ItemFixture WithValidExpiry()
    {
        _item.ExpiryDate = DateTime.Now().AddDays(-1);
        return this;
    }

    public Item Build()
    {
        return _item;
    }
}
```

And when it comes to actually use our Fixture we can do something like this

``` C#
[TestInitialize]
public void Init()
{
    _testItem = ItemFixture()
        .WithPrice(1.5)
        .WithName("Test Item")
        .WithValidExpiry()
        .Build();
}
```

This makes it very easy for someone to find out what certain configurations of a particular class. For example by adding the method ```WithValidExpiry()``` you can easily tell what it means for an ```Item``` to have a valid expiry date.