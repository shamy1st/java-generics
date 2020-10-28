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
    
### Comparable Interface

    public class Main {
        public static void main(String[] args) {
            User user1 = new User(10);
            User user2 = new User(20);

            if(user1.compareTo(user2) > 0) {
                System.out.println("user1 > user2");
            } else if(user1.compareTo(user2) < 0) {
                System.out.println("user1 < user2");
            } else {
                System.out.println("user1 = user2");
            }
        }
    }

    public class User implements Comparable<User> {
        private int points;

        public User(int points) {
            this.points = points;
        }

        @Override
        public int compareTo(User other) {
            if(this.points > other.points) {
                return 1;
            } else if(this.points < other.points) {
                return -1;
            }
            return 0;
        }
    }
    
### Generic Method

    public class Main {
        public static void main(String[] args) {
            double max = Utils.max(1.3, 4.6);
            System.out.println(max);
        }
    }

    public class Utils {
        public static <T extends Comparable<T>> T max(T first, T second) {
            return (first.compareTo(second) > 0) ? first : second;
        }
    }
    
### Class Multiple Type

    public class MyHashMap <K, V> {
        private K key;
        private V value;

        public MyHashMap(K key, V value) {
            this.key = key;
            this.value = value;
        }
    }
    
### Method Multiple Type

    public class Main {
        public static void main(String[] args) {
            Utils.print("key1", 500);
        }
    }

    public class Utils {
        public static <K, V> void print(K key, V value) {
            System.out.println(key + ": "+ value);
        }
    }
    
###     
