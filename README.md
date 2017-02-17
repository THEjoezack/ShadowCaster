# ShadowCaster

This is a copy of the ShadowCasting code from the MSDN Developer Blog of Eric Lippert.

Read more about it in his series of posts on blogs.msdn.microsoft.com:
* [ShadowCasting in C# part One](https://blogs.msdn.microsoft.com/ericlippert/2011/12/12/shadowcasting-in-c-part-one/)
* [ShadowCasting in C# part Two](https://blogs.msdn.microsoft.com/ericlippert/2011/12/15/shadowcasting-in-c-part-two/)
* [ShadowCasting in C# part Three](https://blogs.msdn.microsoft.com/ericlippert/2011/12/19/shadowcasting-in-c-part-three/)
* [ShadowCasting in C# part Four](https://blogs.msdn.microsoft.com/ericlippert/2011/12/22/shadowcasting-in-c-part-four/)
* [ShadowCasting in C# part Five](https://blogs.msdn.microsoft.com/ericlippert/2011/12/27/shadowcasting-in-c-part-five/)
* [ShadowCasting in C# part Six](https://blogs.msdn.microsoft.com/ericlippert/2011/12/29/shadowcasting-in-c-part-six/)

Availabe via [nuget](https://www.nuget.org/packages/ShadowCaster/):
````
Install-Package ShadowCaster
````

Usage Example:
````c#
var cellsInFieldOfView = new List<Cell>(); // will hold our Cell which ARE visible in the field of view

ShadowCaster.ComputeFieldOfViewWithShadowCasting(
  5, // x position of the object doing the viewing
  6, // x position of the object doing the viewing
  4, // The sight radius, represents how far the position can see
  (x,y) => return myMap.getCell(x,y).IsWall(), // Func that returns whether the cell can be seen through
  (x,y) => cellsInFieldOfView.Add(myMap.getCell(x,y)) // Action that specifies what to do with each item that IS in the field of view
);

// Note: myMap and Cell objects are just examples of the types of classes you might use
````
