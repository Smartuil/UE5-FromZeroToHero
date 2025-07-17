# QueueControlFlow

{% stepper %}
{% step %}
### 代码

```cpp
FControlFlow& Flow = FControlFlowStatics::Create(this, TEXT("TestQueueControlFlow"))
.QueueStep(TEXT("ConstructNode"), this, &ThisClass::Construct)
.QueueStep(TEXT("QueueControlFlow"), this, &ThisClass::QueueControlFlow, 0, FString("TestQueueControlFlow"))
.QueueStep(TEXT("DestructNode"), this, &ThisClass::Destruct);

Flow.ExecuteFlow();
```

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## 日志

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## QueueStep执行堆栈

<div align="center" data-full-width="false"><figure><img src="../../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure></div>
{% endstep %}

{% step %}
## ExecuteFlow执行堆栈

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
