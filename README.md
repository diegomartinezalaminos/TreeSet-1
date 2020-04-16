# TreeSet
La clase TreeSet es una subclase de Collection y de AbstractSet. Esta clase tiene una gran particularidad, sus datos estan ordenados en un patron llamado arbol red-black, donde los valores mayores se encuentran en la parte superior del arbol y lentamente se van descomponiendo en los valores menores. Esta clase genera agrupaciones donde los valores nulos no estan permitidos y que no son eficientes a la hora de ordenar sus componentes, tampoco disponen de acceso aleatorio y solo admiten datos que tengan implementado el metodo comparable.
Para implementar un arbol en java deberemos hacerlo de la siguiente manera:
```java
TreeSet<TipoDeVariable> nombreArbol = new Treeset<TipoDeVariable>();
```
Este codigo crearia un arbol vacio, aunque tambien podemos crear un arbol a partir de una coleccion ya existente, para ello hariamos lo siguiente:
```java
TreeSet<TipoDeVariable> nombreArbol = new Treeset<TipoDeVariable (TipoDeColeccion(nombreDeColeccion));
```
En un caso real se veria tal que así:
```java
import java.util.Arrays;
import java.util.TreeSet;

public class Main {
  public static void main(String args[]) throws Exception {

    String nombres[] = { "Alberto", "Antonio", "Jose Luis", "Pedro", "Ana" };
    TreeSet<String> set = new TreeSet<String>(Arrays.asList(nombres));

  }
}
```
Tambien podemos crear un TreeSet con un criterio de comparacion distinto, para ello cuando lo implementemos haremos lo siguiente:
```java
TreeSet(Comparator<? super E> comparator)
```
En un caso real, el codigo se veria de la siguiente forma:
```java
import java.util.Comparator;
import java.util.TreeSet;

public class ComparableTree {
  public static void main(String args[]){
  TreeSet<Empl> salComp = new TreeSet<Empleado>(new CompSalario());
  salComp.add(new Empleado("Juan",3900));
  salComp.add(new Empleado("Paco",2000));
  salComp.add(new Empleado("Miguel",2500));
  salComp.add(new Empleado("Luis",1900));
  
  for (Empleado e : salComp) {
  System.out.println(e);
  }
  }
}
class CompSalario implements Comparator<Empleado>{
 
    @Override
    public int compare(Empleado e1, Empleado e2) {
        if(e1.getSalario() > e2.getSalario()){
            return 1;
        } else {
            return -1;
        }
    }
}
class Empleado{
     
    private String nombre;
    private int salario;
     
    public Empleado(String n, int s){
        this.nombre = n;
        this.salary = s;
    }
     
    public String getName() {
        return nombre;
    }
    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
    public int getSalario() {
        return salario;
    }
    public void setSalario(int salario) {
        this.salario = salario;
    }
    public String toString(){
        return "nombre: "+this.nombre+"-- salario: "+this.salario;
    }
}
```

Usando Arboles tenemos a nuestra disposicion bastantes metodos para manipularlos, entre ellos vamos a destacar los siguientes:

#### add(E) y add(Collection)
Permite añadir un elemento o serie de elementos.

#### clear()
Eliminar todos los valores dentro del arbol.

#### contains(Object)
Devuelve un booleano indicando si el elemento mencionado existe dentro del arbol.

#### descendingIterator()
Devuelve un iterador de los elementos en orden descendente

#### last() y lower()
Devuelve el mayor y menos valor dela rbol respectivamente.

#### pollLast() y pollFirst()
Devuelve y elimina del arbol el mayor y menos valor respectivamente.

#### clone
Crea una copia del arbol.
