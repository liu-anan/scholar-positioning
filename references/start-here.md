# 新用户黄金路径

如果你是第一次接触 `scholar-positioning`，不要从所有文档一起读起。  
按下面这条路径走就够了。

## 你先判断自己属于哪种情况

### 情况 A：我只想先试一次，看它能不能用

按这个顺序：

1. 看 `README.md`
2. 看 [users/onboarding-prompt.md](./users/onboarding-prompt.md)
3. 完成一次最小 personalize
4. 跑一个单学者 `full-profile`
5. 再跑一个多学者 `positioning`

### 情况 B：我想正式装给组里同学用

按这个顺序：

1. 看 `README.md`
2. 看本文件
3. 看 [source-of-truth.md](./source-of-truth.md)
4. 看 [core/artifact-contract.md](./core/artifact-contract.md)
5. 看 [core/source-pack-contract.md](./core/source-pack-contract.md)
6. 看 [domains/domain-pack-contract.md](./domains/domain-pack-contract.md)
7. 看 [users/user-overlay-contract.md](./users/user-overlay-contract.md)
8. 最后看 [eval/rubric.md](./eval/rubric.md)

### 情况 C：我只想拆一个学者

你只需要：

1. 做不做 personalize 都行
2. 直接走 `full-profile`
3. 不要默认做 map

### 情况 D：我想比较多个学者

你需要：

1. 先确认这些学者有没有可复用 `full-profile`
2. 没有就先补档
3. 再做 `positioning`

不要从名字列表直接跳到强 map 结论。

---

## 推荐的第一次完整体验

### 第 1 步：安装

确保 skill 目录中至少有：

- `SKILL.md`
- `README.md`
- `references/`

### 第 2 步：做首次启动问答

读：

- [users/onboarding.md](./users/onboarding.md)
- [users/onboarding-prompt.md](./users/onboarding-prompt.md)
- [users/onboarding-mapping.zh-CN.md](./users/onboarding-mapping.zh-CN.md)

如果你想看最后会长成什么样，再看：

- [users/examples/onboarding-output.preferences.example.md](./users/examples/onboarding-output.preferences.example.md)

### 第 3 步：跑一个单学者

先验证 `full-profile`。

目标不是看它写得多华丽，而是看：

- 能不能把这个人真正建清楚
- 有没有保留证据边界
- 有没有过早压缩成薄摘要

### 第 4 步：再跑一个多学者

再验证 `positioning`。

重点看：

- 差异是不是前置
- 主簇和桥梁是不是清楚
- 有没有把弱关系伪装成事实

### 第 5 步：最后才考虑 roadmap

只有上游 `profile` 和 `positioning` 稳了，roadmap 才有意义。

---

## 三个最重要的使用边界

1. `profile` 不能被 `map` 反推  
2. `roadmap` 不是默认产物  
3. 弱证据不能支撑强结论  

---

## 你不需要一开始就读的东西

第一次上手时，通常不需要立刻细读：

- 所有 eval checklist
- 所有 taxonomy 维护规则
- 所有 roadmap 细则

这些更适合维护者或第二阶段扩展时再看。

但如果你这次是在改协议结构，而不是第一次试用，就不要跳过：

- [core/artifact-contract.md](./core/artifact-contract.md)
- [core/source-pack-contract.md](./core/source-pack-contract.md)
- [eval/rubric.md](./eval/rubric.md)
