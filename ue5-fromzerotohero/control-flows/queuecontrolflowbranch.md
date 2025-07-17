# QueueControlFlowBranch

{% stepper %}
{% step %}
### 代码

```cpp
FControlFlow& Flow = FControlFlowStatics::Create(this, TEXT("TestQueueControlFlowBranch"))
.QueueStep(TEXT("ConstructNode"), this, &ThisClass::Construct)
.BranchFlow([this](TSharedRef<FControlFlowBranch> Branch)
{
	Branch->AddOrGetBranch(1).QueueStep(TEXT("QueueControlFlowBranch1"), this, &ThisClass::QueueControlFlowBranch1, 1, FString("TestQueueControlFlowBranch1"));
	Branch->AddOrGetBranch(2).QueueStep(TEXT("QueueControlFlowBranch2"), this, &ThisClass::QueueControlFlowBranch2, 2, FString("TestQueueControlFlowBranch2"));
	
	return FMath::RandBool() ? 1 : 2;
})
.QueueStep(TEXT("DestructNode"), this, &ThisClass::Destruct);

Flow.ExecuteFlow();
```

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## 日志

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## QueueStep执行堆栈

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
## ExecuteFlow执行堆栈

<figure><img src="../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
