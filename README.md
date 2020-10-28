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
    
### 
