# TaskTagger
分析一句话里的时间与事情

## Usage
- 将nmodel引入工程
- 代码实现
```
 		guard let model = try? TaskTagger(configuration: .init())
        else { return }
        
        

        let text = "明天上午10点开会"
        
        // 用模型进行文本分类
        guard let pre = try? model.prediction(text: text) else {
            fatalError("Failed to make predictions")
        }
        
        let keys = pre.labels
        let values = pre.tokens
        let map = Dictionary(zip(keys, values), uniquingKeysWith: { (first, second) in "\(first)\(second)" })

        print(map)
````