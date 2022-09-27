# Numberクラス
```java
abstract class Number {
    protected String type;

    public String getType() {
        return type;
    }
    public abstract void show();
    public abstract void add(Number n);
}

```
classの前にabstractを付けると抽象クラスになる。

メソッドの前にabstractを付けると抽象メソッドになる。

中小クラスからインスタンスを作ることはできない

そして、この抽象クラスNumberを継承してサブクラスを定義していく

# Integerクラス
```java
class Integer extends Number {
    private int value;

    public Integer(int value) {
        this.value = value;
        type = "整数";
    }
    public void increment() {
        value++;
    }
    public void show() {
        System.out.printf("%d: %s\n", value, type);
    }
    public void add(Number n) {
    //演算子instanceofは、インスタンスのクラスを判別する。
    //仮引数nの型はNumberのため、サブクラスIntegerにキャストしている
        if(n instanceof Integer) {
            this.value += ((Integer) n).value;
        } else {
            System.out.println("型が異なります");
        }
    }
}
```

inenceはインスタンスのクラスを判別する。
