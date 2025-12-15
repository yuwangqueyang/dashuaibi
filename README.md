graph TD
    %% 定义节点样式（每个属性用 ; 分隔，类名清晰）
    classDef cnnBlock fill:#f08ff; stroke:#4682B4; stroke-width:2px; rx:8; ry:8; font-weight:bold;
    classDef inputOutput fill:#f5f5f5; stroke:#2F4F4F; stroke-width:3px; rx:8; ry:8; font-weight:bold;
    classDef poolBlock fill:#e6f7ff; stroke:#1890ff; stroke-width:2px; rx:8; ry:8; font-weight:bold;

    %% 子图：3D卷积块流程
    subgraph CNN_Block_3D
        %% 节点定义（含HTML换行<br>，应用对应样式类:::类名）
        A["📦 Input<br>(10×seq_len 3D张量)"]:::inputOutput
        B["Conv<br>(3×3×256 卷积核)"]:::cnnBlock
        C["ReLU<br>(非线性激活)"]:::cnnBlock
        D["Aver-pooling<br>(2×2 池化核)"]:::poolBlock
        E["ReLU<br>(非线性激活)"]:::cnnBlock
        F["Conv<br>(3×3×256 卷积核)"]:::cnnBlock
        G["ReLU<br>(非线性激活)"]:::cnnBlock
        H["📦 Output<br>(256×new_seq 3D张量)"]:::inputOutput

        %% 流程链接（A→B → G→H 共7条边）
        A --> B
        B --> C
        C --> D
        D --> E
        E --> F
        F --> G
        G --> H
    end

    %% 链接样式（7条边对应7个linkStyle，索引0~6）
    linkStyle 0 stroke:#4682B4; stroke-width:2px; arrowhead:normal;
    linkStyle 1 stroke:#4682B4; stroke-width:2px; arrowhead:normal;
    linkStyle 2 stroke:#1890ff; stroke-width:2px; arrowhead:normal;
    linkStyle 3 stroke:#4682B4; stroke-width:2px; arrowhead:normal;
    linkStyle 4 stroke:#4682B4; stroke-width:2px; arrowhead:normal;
    linkStyle 5 stroke:#4682B4; stroke-width:2px; arrowhead:normal;
    linkStyle 6 stroke:#2F4F4F; stroke-width:2px; arrowhead:normal;
