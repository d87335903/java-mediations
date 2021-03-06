
第1章 简介<br>
1.1 并发简史<br>
1.2 线程的优势<br>
1.2.1 发挥多处理器的强大能力<br>
1.2.2 建模的简单性<br>
1.2.3 异步事件的简化处理<br>
1.2.4 响应更灵敏的用户界面<br>
1.3 线程带来的风险<br>
1.3.1 安全性问题<br>
1.3.2 活跃性问题<br>
1.3.3 性能问题<br>
1.4 线程无处不在<br>
部分 基础知识<br>  
第2章 线程安全性<br>
2.1 什么是线程安全性<br>
2.2 原子性<br>
2.2.1 竞态条件<br>
2.2.2 示例：延迟初始化中的竞态条件<br>
2.2.3 复合操作<br>
2.3 加锁机制<br>
2.3.1 内置锁<br>
2.3.2 重入<br>
2.4 用锁来保护状态<br>
2.5 活跃性与性能(there)<br>
第3章 对象的共享<br>
3.1 可见性<br>
3.1.1 失效数据<br>
3.1.2 非原子的64位操作<br>
3.1.3 加锁与可见性<br>
3.1.4 Volatile变量<br>
3.2 发布与逸出<br>
3.3 线程封闭<br>
3.3.1 Ad-hoc线程封闭<br>
3.3.2 栈封闭<br>
3.3.3 ThreadLocal类<br>
3.4 不变性<br>
3.4.1 Final域<br>
3.4.2 示例：使用Volatile类型来发布不可变对象<br>
3.5 安全发布<br>
3.5.1 不正确的发布：正确的对象被破坏<br>
3.5.2 不可变对象与初始化安全性<br>
3.5.3 安全发布的常用模式<br>
3.5.4 事实不可变对象<br>
3.5.5 可变对象<br>
3.5.6 安全地共享对象<br>
第4章 对象的组合<br>
4.1 设计线程安全的类<br>
4.1.1 收集同步需求<br>
4.1.2 依赖状态的操作<br>
4.1.3 状态的所有权<br>
4.2 实例封闭<br>
4.2.1 Java监视器模式<br>
4.2.2 示例：车辆追踪<br>
4.3 线程安全性的委托<br>
4.3.1 示例：基于委托的车辆追踪器<br>
4.3.2 独立的状态变量<br>
4.3.3 当委托失效时<br>
4.3.4 发布底层的状态变量<br>
4.3.5 示例：发布状态的车辆追踪器<br>
4.4 在现有的线程安全类中添加功能<br>
4.4.1 客户端加锁机制<br>
4.4.2 组合<br>
4.5 将同步策略文档化<br>
第5章 基础构建模块<br>
5.1 同步容器类<br>
5.1.1 同步容器类的问题<br>
5.1.2 迭代器与Concurrent-ModificationException<br>
5.1.3 隐藏迭代器<br>
5.2 并发容器<br>
5.2.1 ConcurrentHashMap<br>
5.2.2 额外的原子Map操作<br>
5.2.3 CopyOnWriteArrayList<br>
5.3 阻塞队列和生产者-消费者模式<br>
5.3.1 示例：桌面搜索<br>
5.3.2 串行线程封闭<br>
5.3.3 双端队列与工作密取<br>
5.4 阻塞方法与中断方法<br>
5.5 同步工具类<br>
5.5.1 闭锁<br>
5.5.2 FutureTask<br>
5.5.3 信号量<br>
5.5.4 栅栏<br>
5.6 构建高效且可伸缩的结果缓存<br>
第二部分 结构化并发应用程序<br>
第6章 任务执行<br>
6.1 在线程中执行任务<br>
6.1.1 串行地执行任务<br>
6.1.2 显式地为任务创建线程<br>
6.1.3 无限制创建线程的不足<br>
6.2 Executor框架<br>
6.2.1 示例：基于Executor的Web服务器<br>
6.2.2 执行策略<br>
6.2.3 线程池<br>
6.2.4 Executor的生命周期<br>
6.2.5 延迟任务与周期任务<br>
6.3 找出可利用的并行性<br>
6.3.1 示例：串行的页面渲染器<br>
6.3.2 携带结果的任务Callable与Future<br>
6.3.3 示例：使用Future实现页面渲染器<br>
6.3.4 在异构任务并行化中存在的局限<br>
6.3.5 CompletionService:Executor与BlockingQueue<br>
6.3.6 示例：使用CompletionService实现页面渲染器<br>
6.3.7 为任务设置时限<br>
6.3.8 示例：旅行预定门户网站<br>
第7章 取消与关闭<br>
7.1 任务取消<br>
7.1.1 中断<br>
7.1.2 中断策略<br>
7.1.3 响应中断<br>
7.1.4 示例：计时运行<br>
7.1.5 通过Future来实现取消<br>
7.1.6 处理不可中断的阻塞<br>
7.1.7 采用newTaskFor来封装非标准的取消<br>
7.2 停止基于线程的服务<br>
7.2.1 示例：日志服务<br>
7.2.2 关闭ExecutorService<br>
7.2.3 “毒丸”对象<br>
7.2.4 示例：只执行一次的服务<br>
7.2.5 shutdownNow的局限性<br>
7.3 处理非正常的线程终止<br>
7.4 JVM关闭<br>
7.4.1 关闭钩子<br>
7.4.2 守护线程<br>
7.4.3 终结器<br>
第8章 线程池的使用<br>
8.1 在任务与执行策略之间的隐性耦合<br>
8.1.1 线程饥饿死锁<br>
8.1.2 运行时间较长的任务<br>
8.2 设置线程池的大小<br>
8.3 配置ThreadPoolExecutor<br>
8.3.1 线程的创建与销毁<br>
8.3.2 管理队列任务<br>
8.3.3 饱和策略<br>
8.3.4 线程工厂<br>
8.3.5 在调用构造函数后再定制ThreadPoolExecutor<br>
8.4 扩展 ThreadPoolExecutor<br>
8.5 递归算法的并行化<br>
第9章 图形用户界面应用程序<br>
9.1 为什么GUI是单线程的<br>
9.1.1 串行事件处理<br>
9.1.2 Swing中的线程封闭机制<br>
9.2 短时间的GUI任务<br>
9.3 长时间的GUI任务<br>
9.3.1 取消<br>
9.3.2 进度标识和完成标识<br>
9.3.3 SwingWorker<br>
9.4 共享数据模型<br>
9.4.1 线程安全的数据模型<br>
9.4.2 分解数据模型<br>
9.5 其他形式的单线程子系统<br>
第三部分 活跃性、性能与测试<br>
第10章 避免活跃性危险<br>
10.1 死锁<br>
10.1.1 锁顺序死锁<br>
10.1.2 动态的锁顺序死锁<br>
10.1.3 在协作对象之间发生的死锁<br>
10.1.4 开放调用<br>
10.1.5 资源死锁<br>
10.2 死锁的避免与诊断<br>
10.2.1 支持定时的锁<br>
10.2.2 通过线程转储信息来分析死锁<br>
10.3 其他活跃性危险<br>
10.3.1 饥饿<br>
10.3.2 糟糕的响应性<br>
10.3.3 活锁<br>
第11章 性能与可伸缩性<br>
11.1 对性能的思考<br>
11.1.1 性能与可伸缩性<br>
11.1.2 评估各种性能权衡因素<br>
11.2 Amdahl定律<br>
11.2.1 示例：在各种框架中隐藏的串行部分<br>
11.2.2 Amdahl定律的应用<br>
11.3 线程引入的开销<br>
11.3.1 上下文切换<br>
11.3.2 内存同步<br>
11.3.3 阻塞<br>
11.4 减少锁的竞争<br>
11.4.1 缩小锁的范围（“快进快出”）<br>
11.4.2 减小锁的粒度<br>
11.4.3 锁分段<br>
11.4.4 避免热点域<br>
11.4.5 一些替代独占锁的方法<br>
11.4.6 监测CPU的利用率<br>
11.4.7 向对象池说“不”<br>
11.5 示例：比较Map的性能<br>
11.6 减少上下文切换的开销<br>
第12章 并发程序的测试<br>
12.1 正确性测试<br>
12.1.1 基本的单元测试<br>
12.1.2 对阻塞操作的测试<br>
12.1.3 安全性测试<br>
12.1.4 资源管理的测试<br>
12.1.5 使用回调<br>
12.1.6 产生更多的交替操作<br>
12.2 性能测试<br>
12.2.1 在PutTakeTest中增加计时功能<br>
12.2.2 多种算法的比较<br>
12.2.3 响应性衡量<br>
12.3 避免性能测试的陷阱<br>
12.3.1 垃圾回收<br>
12.3.2 动态编译<br>
12.3.3 对代码路径的不真实采样<br>
12.3.4 不真实的竞争程度<br>
12.3.5 无用代码的消除<br>
12.4 其他的测试方法<br>
12.4.1 代码审查<br>
12.4.2 静态分析工<br>具<br>
12.4.3 面向方面的测试技术<br>
12.4.4 分析与监测工具<br>
第四部分 高级主题<br>
第13章 显式锁<br>
13.1 Lock与 ReentrantLock<br>
13.1.1 轮询锁与定时锁<br>
13.1.2 可中断的锁获取操作<br>
13.1.3 非块结构的加锁<br>
13.2 性能考虑因素<br>
13.3 公平性<br>
13.4 在synchronized和ReentrantLock之间进行选择<br>
13.5 读-写锁<br>
第14章 构建自定义的同步工具<br>
14.1 状态依赖性的管理<br>
14.1.1 示例：将前提条件的失败传递给调用者<br>
14.1.2 示例：通过轮询与休眠来实现简单的阻塞<br>
14.1.3 条件队列<br>
14.2 使用条件队列<br>
14.2.1 条件谓词<br>
14.2.2 过早唤醒<br>
14.2.3 丢失的信号<br>
14.2.4 通知<br>
14.2.5 示例：阀门类<br>
14.2.6 子类的安全问题<br>
14.2.7 封装条件队列<br>
14.2.8 入口协议与出口协议<br>
14.3 显式的Condition对象<br>
14.4 Synchronizer剖析<br>
14.5 AbstractQueuedSynchronizer<br>
14.6 java.util.concurrent同步器类中的 AQS<br>
14.6.1 ReentrantLock<br>
14.6.2 Semaphore与CountDownLatch<br>
14.6.3 FutureTask<br>
14.6.4 ReentrantReadWriteLock<br>
第15章 原子变量与非阻塞同步机制<br>
15.1 锁的劣势<br>
15.2 硬件对并发的支持<br>
15.2.1 比较并交换<br>
15.2.2 非阻塞的计数器<br>
15.2.3 JVM对CAS的支持<br>
15.3 原子变量类<br>
15.3.1 原子变量是一种“更好的volatile”<br>
15.3.2 性能比较：锁与原子变量<br>
15.4 非阻塞算法<br>
15.4.1 非阻塞的栈<br>
15.4.2 非阻塞的链表<br>
15.4.3 原子的域更新器<br>
15.4.4 ABA问题<br>
第16章 Java内存模型<br>
16.1 什么是内存模型，为什么需要它<br>
16.1.1 平台的内存模型<br>
16.1.2 重排序<br>
16.1.3 Java内存模型简介<br>
16.1.4 借助同步<br>
16.2 发布<br>
16.2.1 不安全的发布<br>
16.2.2 安全的发布<br>
16.2.3 安全初始化模式<br>
16.2.4 双重检查加锁<br>
16.3 初始化过程中的安全性<br>
