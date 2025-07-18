# QueueStep

{% stepper %}
{% step %}
### 代码

```cpp
FControlFlow& Flow = FControlFlowStatics::Create(this, TEXT("TestQueueStep"))
	.QueueStep(TEXT("ConstructNode"), this, &ThisClass::Construct)
	.QueueStep(TEXT("Foo"), this, &ThisClass::Foo)
	.QueueStep(TEXT("DestructNode"), this, &ThisClass::Destruct);

Flow.ExecuteFlow();
```

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>


{% endstep %}

{% step %}
## 日志

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## QueueStep执行堆栈

<figure><img src="../../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ExecuteFlow执行堆栈

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
