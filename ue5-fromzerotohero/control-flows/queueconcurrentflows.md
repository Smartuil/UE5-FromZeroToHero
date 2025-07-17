# QueueConcurrentFlows

{% stepper %}
{% step %}
### 代码

```cpp
FControlFlow& Flow = FControlFlowStatics::Create(this, TEXT("TestQueueControlFlowBranch"))
.QueueStep(TEXT("ConstructNode"), this, &ThisClass::Construct)
.ForkFlow([this](TSharedRef<FConcurrentControlFlows> ConcurrentFlows)
{
	ConcurrentFlows->AddOrGetFlow(0).QueueStep(TEXT("QueueConcurrentFlows1"), this, &ThisClass::QueueConcurrentFlows1, 1, FString("QueueConcurrentFlows1"));
	ConcurrentFlows->AddOrGetFlow(1).QueueStep(TEXT("QueueConcurrentFlows2"), this, &ThisClass::QueueConcurrentFlows2, 2, FString("QueueConcurrentFlows2"));
})
.QueueStep(TEXT("DestructNode"), this, &ThisClass::Destruct);

Flow.ExecuteFlow();
```

<figure><img src="../../.gitbook/assets/image (18).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## 日志

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## QueueStep执行堆栈

<figure><img src="../../.gitbook/assets/image (20).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ExecuteFlow执行堆栈

<figure><img src="../../.gitbook/assets/image (21).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
