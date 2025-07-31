### LECT2：static的作用

静态方法相当于一个通用工具，不用创建对象就能使用。（一个整体）

```java
//Dog.java

public class Dog {
    public void MakeNoise() {
        System.out.println("Bark");
    }
}

//no main method, can't be run directly
```

```java
//DogLaucher.java

public class DogLauncher {
    public static void main(String[] args) {
        Dog.MakeNoise();
    }
}
```

而非静态方法需要实例化。（整体下的每个个体的区别）

```java
//Dog.java

public class Dog {

    public int weightInPounds;

    public Dog(int w) {
        weightInPounds = w;
    }

    public void MakeNoise() {
        if (weightInPounds < 10) {
            System.out.println("yipyipyip");
        }

        else if (weightInPounds < 30) {
            System.out.println("Bark");
        }

        else {
            System.out.println("aroooooo");
        }
    }
}

//no main method, can't be run directly
```

```java
//DogLauncher.java

public class DogLauncher {
    public static void main(String[] args) {
        Dog dog1 = new Dog(20);
        //dog1.weightInPounds = 20;
        dog1.MakeNoise();
    }
}
```

非静态方法相比之下更加多元化，而静态方法更通用，适合简单的操作。（模块化和自定义化）

**静态方法与非静态方法使用的区别比较。**

```java
//Dog.java


public class Dog {

    public int weightInPounds;
    public static String binomen = "Canis familiaris";

    public Dog(int w) {
        weightInPounds = w;
    }

    public void MakeNoise() {
        if (weightInPounds < 10) {
            System.out.println("yipyipyip");
        }

        else if (weightInPounds < 30) {
            System.out.println("Bark");
        }

        else {
            System.out.println("aroooooo");
        }
    }

    public static Dog maxDog(Dog d1, Dog d2) {
        if (d1.weightInPounds > d2.weightInPounds) {
            return d1;
        }
        else {
            return d2;
        }
    }

    public Dog maxDog(Dog d3) {
        if (weightInPounds > d3.weightInPounds) {
            return this;
        }

        else return d3;
    }
}

//no main method, can't be run directly
```

```java
//DogLauncher.java

public class DogLauncher {
    public static void main(String[] args) {
        Dog doga = new Dog(20);
        Dog dogb = new Dog(3);
        System.out.println(Dog.maxDog(doga, dogb).weightInPounds);

        Dog dogc = new Dog(120);
        Dog dogd = new Dog(20);
        System.out.println(dogc.maxDog(dogd).weightInPounds);


        System.out.println(Dog.binomen);
        //Dog.maxDog(doga, dogb) 和 doga.maxDog(dogb) 的区别
    }
}
```