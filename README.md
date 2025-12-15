graph TD
    %% 定义3D风格样式类（模拟立体块、渐变、边框）
    classDef cnnBlock fill:#f0f8ff,stroke:#4682B4,stroke-width:2px,rx:8,ry:8,font-weight:bold;
    classDef inputOutput fill:#f5f5f5,stroke:#2F4F4F,stroke-width:3px,rx:8,ry:8,font-weight:bold;
    classDef poolBlock fill:#e6f7ff,stroke:#1890ff,stroke-width:2px,rx:8,ry:8,font-weight:bold;
    
    %% 流程节点（模拟3D块命名+层级）
    subgraph CNN_Block_3D
        A["📥 Input<br/>(三维输入层)"]:::inputOutput --> B["Conv<br/>(卷积层)"]:::cnnBlock
        B --> C["ReLU<br/>(激活层)"]:::cnnBlock
        C --> D["Aver-pooling<br/>(平均池化层)"]:::poolBlock
        D --> E["ReLU<br/>(激活层)"]:::cnnBlock
        E --> F["Conv<br/>(卷积层)"]:::cnnBlock
        F --> G["ReLU<br/>(激活层)"]:::cnnBlock
        G --> H["📤 Output<br/>(三维输出层)"]:::inputOutput
    end
    
    %% 箭头样式（模拟3D流程线）
    linkStyle 0 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 1 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 2 stroke:#1890ff,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 3 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 4 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 5 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 6 stroke:#2F4F4F,stroke-width:2px,arrowheadStyle:filled;
