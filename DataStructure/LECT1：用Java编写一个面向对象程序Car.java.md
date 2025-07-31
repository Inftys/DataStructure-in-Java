### LECT1：用Java编写一个面向对象程序Car.java

```java
public class Car {
    String model;
    int wheels;

    public Car(String defModel, int wheelNum) {
        this.model = defModel;
        this.wheels = wheelNum;
    }

    public void driveCar() {
        if (this.wheels < 4) {
            System.out.println("Whoops, fail to vroom");
            return;
        }

        System.out.println("Success to VROOM");
    }

    public int getWheels() {
        return this.wheels;
    }

    public void driveIntoDitch(int wheelsLost) {
        this.wheels -= wheelsLost;
    }

    public static void main(String[] args) {
        Car op1;
        Car op2;
        op1 = new Car("Benz", 4);
        op2 = new Car("Toyota", 4);

        op1.driveCar();
        op1.driveIntoDitch(1);
        System.out.println(op1.getWheels());
        op1.driveCar();
    }
}
```

Java的面向对象程序总体与C++有许多相似之处。