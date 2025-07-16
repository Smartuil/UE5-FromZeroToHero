# QueueWait

{% stepper %}
{% step %}
### 代码

```cpp
FControlFlow& Flow = FControlFlowStatics::Create(this, TEXT("TestQueueWait"))
.QueueStep(TEXT("ConstructNode"), this, &ThisClass::Construct)
.QueueStep(TEXT("QueueWaitFunction"), this, &ThisClass::QueueWaitFunction)
.QueueStep(TEXT("DestructNode"), this, &ThisClass::Destruct);

Flow.ExecuteFlow();
```

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## 日志

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## QueueStep执行堆栈

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ExecuteFlow执行堆栈

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
