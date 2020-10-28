# Java Generics

### Generic Class

    public class Main {
        public static void main(String[] args) {
            GenericList<Integer> list = new GenericList<>();
            list.add(5);
            System.out.println(list.get(0));
        }
    }

    public class GenericList<T> {
        private T[] items = (T[]) new Object[10];
        private int count;

        public void add(T item) {
            items[count++] = item;
        }

        public T get(int index) {
            return items[index];
        }
    }
    
### Constraints

    //only for types Number and classes inherit from it
    public class GenericList<T extends Number> {
        ...
    }

    //only for types implements Comparable & Cloneable interfaces
    public class GenericList<T extends Comparable & Cloneable> {
        ...
    }
    
### 
