第2章 一切都是对象
    
    1.在使用任何引用前，都必须为其指定一个对象，如果试图访问一个为null的引用，将会报错。
    
    2.java有一个垃圾回收器，用来监视所有new创建的对象，并辨别那些不在被引用的对象，释放这些对象的内存空间。
    
    3.当一个类的成员变量是基本类型是，JVM会默认将其初始化为对应的初值，但是最好自行进行初始化。
    
    4.方法名和参数列表（合起来称为“方法签名”）唯一的标志出某个方法。
    
    5.若返回值类型是void，则return关键字的意思是退出当前方法。
    
    6.static关键字
        创建一个类就是描述这个类的对象的外观和行为。通常来说，我们用new创建对象后，才能调用这个对象的方法。否则，并未获得任何对象。
        通常，我们需要创建一个对象，来访问这个对象的数据或方法，因为非static域和方法必须和必须和某一特定对象相关联。
        
    7.break,continue关键字
        break是强行退出循环，不执行循环中剩余的语句，而continue是结束当前循环，回到循环的起始处，开始下一次循环。
        
第5章

    5.1 用构造器确保初始化
        在对类进行初始化前，会先初始化类中的变量。也即是会先对成员变量进行初始化。
        
    5.4 this关键字返回了当前对象的引用。
        this关键字对于将当前对象传递给其他方法也是很有用。
        还可以用this调用构造器，必须放在构造器的第一行。
        static的含义：static方法就是没有this的方法。
        
    5.5 清理：终结处理和垃圾回收
        finalize的工作原理：一旦垃圾回收器准备释放对象占用的空间，将首先调用其finalize方法，并且在下一次垃圾回收时，才会真正回收对象占用的内存。
                            也就是说，即使调用了finalize方法，对象的内存也不一定会释放。
                            
         判断对象是否存活：引用计数，可达性分析
         垃圾回收的方式：复制算法,标记-清除算法，标记-整理算法等
    5.7 构造器初始化
        在对构造器进行初始化前，会首先对成员变量进行初始化。
        
        总结一下：对象的创建的过程（加入类为Dog）
            1.构造器实际上也是一个static方法，当首次创建类型为Dog的对象时，Java解释器必须查找类路径，以定位Dog.class文件。
            2.然后载入Dog.class（这将创建一个Class对象），有关静态初始化的所有动作都会执行。因此，静态初始化只在Class对象首次加载的时候进行一次。
            3.当用new Dog()的时候，首先将在堆上为Dog分配足够的存储空间。
            4.这块空间会被清零，这就自动的将类中的所有基本类型初始化为默认值，而引用设置为null。
            5.执行所有字段的初始化动作。
            6.执行构造器。   
    5.9 枚举类型
        枚举类型里面的常量要大写
        enum事实上就是一个类，并且具有自己的方法。
        
第六章 访问权限控制

    6.1 当编写一个Java源代码文件时，只能有一个public类，且这个类的名称要和源代码文件的名称相同。 Java包名全部使用小写。不用遵守驼峰命名法。      
    6.2 java访问权限修饰词
        public：访问权限最大，其他包内也可以访问。
        protected：也具有包访问权限，但它仍旧不是public的。其它包中的这个类的子类可以访问，
        默认的包访问权限：
        private：只有本类中可以访问。
    6.4 类的访问权限
        注意：类既不可以使private的，也不可以是protected的。
        控制对成员的访问权限有两个原因：第一是为了用户不要触碰那些他们不该触碰的部分，这些部分对于类内部的操作是必要的，但是它并不属于客户端程序员所需接口的一部分。
            第二是为了让类库设计者可以更改类的内部的工作方式，而不必担心这样会对客户端程序员产生重大的影响。
            
第七章 复用类

    7.1 对对象的引用进行初始化的四种方式
        1.在定义对象的地方，这意味着它们总是能够在调用构造器之前进行初始化。
        2.在构造器里面。
        3.使用实例初始化
        4.就是在要使用这些对象之前，这种方式称为惰性初始化。在生成对象不值得或者不必每次都生成对象的情况下，这种方式可以减少额外的负担。
        
    7.2 当创建一个类时，总是在继承，因此，除非已明确指出要从其他类中继承，否则就是默认的从Object根类继承。
        
        
        
            
    