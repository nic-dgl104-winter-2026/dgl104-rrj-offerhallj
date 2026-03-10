# Design Patterns
## The Abstract Factory Pattern
The Abstract Factory Pattern is a creational design pattern used to create instances of related objects without specifying a concrete class. This is achieved by creating abstract interfaces for the objects which you wish to create and then creating an abstract Factory class to return an object implementing that interface. For example:

```C#
public abstract class ComputerFactory {
    public virtual IComputer CreateComputer();
}

public interface IComputer {
    // . . . computer methods . . . //
}


public class Laptop : IComputer {
    // . . .
}

public class Desktop : IComputer {
    // . . .
}
```

The abstract ComputerFactory class defines the CreateComputer method which returns an object implementing the IComputer interface. Laptop and Desktop both implement this interface. Next, we can concrete factory classes which inherit from the abstract ComputerFactory and which handle the creation of our IComputer variants.

```C#
public class LaptopFactory : ComputerFactory {
    public override IComputer CreateComputer() {
        return new Laptop();
    }
}

public class DesktopFactory : ComputerFactory {
    public override IComputer CreateComputer() {
        return new Desktop();
    }
}
```

Using this pattern, we now have a way of creating and interacting with IComputer objects without having to specify which specific type of computer we are creating. All we have to do is create a variable in our object to cache an subclass of ComputerFactory. We can assign this variable to either an instance of LaptopFactory or DesktopFactory and our code will work just the same.

```C#
public class ManufacturingFacility {
    readonly ComputerFactory _computerFactory;

    public ManufacturingFacility(ComputerFactory factory) {
        _computerFactory = factory;
    }
}
```

Our ManufacturingFacility class can create any type of computer without having to know what type it's creating or which factory it is implementing.

## The Adapter Pattern
The Adapter Pattern is a structural design pattern which allows incompatible objects to interact with one another without making changes to their underlying source code. This is achieved by creating an adapter class which the interface of the incompatible class can interact with. A good example of this is the RecyclerView Adapter in Android studio. The underlying code of the RecyclerView relies upon certain methods contained within the RecyclerView.Adapter class, and by extending this class in a custom Adapter class, the developer can adapt their user-defined classes to interact with the RecyclerView. 

As an example, this CalculatorAdapter class allows a list of  Calculation objects to be displayed in a RecyclerView by defining the ViewHolder and overriding the adapter methods.

```kotlin
class CalculationAdapter(val calculationHistory: List<Calculation>) : RecyclerView.Adapter<CalculationAdapter.ViewHolder>() {
    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): ViewHolder {
        val view = LayoutInflater.from(parent.context)
            .inflate(R.layout.calculation_item, parent, false)

        return ViewHolder(view)
    }

    override fun onBindViewHolder(holder: ViewHolder, position: Int) {
        holder.textView.text = calculationHistory[position].print(withResult = true)
    }

    override fun getItemCount(): Int {
        return calculationHistory.count()
    }

    class ViewHolder(view: View): RecyclerView.ViewHolder(view) {
        val textView: TextView = view.findViewById(R.id.txt_calculation)
    }
}
```

## The Mediator Pattern
The Mediator Pattern is a behavioural pattern which allows different objects to interact with one another without creating dependencies. Instead of interacting directly, objects only interact with an mediator object which coordinates the interactions. An example of thisis the ViewModel class in android MVVM architecture. The ViewModel is responsible for receiving and delegating information between the View and Model classes, ensuring neither object needs to know about or be dependent upon the other. This not only helps to make the code cleaner, but it also makes it more modular, as the same Model of View functions can be used in different ways dependin upon how data is passed through the mediator.
