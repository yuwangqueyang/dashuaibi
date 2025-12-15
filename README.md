graph TD
    classDef cnnBlock fill:#f0f8ff,stroke:#4682B4,stroke-width:2px,rx:8,ry:8,font-weight:bold;
    classDef inputOutput fill:#f5f5f5,stroke:#2F4F4F,stroke-width:3px,rx:8,ry:8,font-weight:bold;
    classDef poolBlock fill:#e6f7ff,stroke:#1890ff,stroke-width:2px,rx:8,ry:8,font-weight:bold;

    subgraph CNN_Block_3D
        A["📥 Input<br/>(10×seq_len 3D张量)"]::inputOutput
        B["Conv<br/>(3×3×256 卷积核)"]::cnnBlock
        C["ReLU<br/>(非线性激活)"]::cnnBlock
        D["Aver-pooling<br/>(2×2 池化核)"]::poolBlock
        E["ReLU<br/>(非线性激活)"]::cnnBlock
        F["Conv<br/>(3×3×256 卷积核)"]::cnnBlock
        G["ReLU<br/>(非线性激活)"]::cnnBlock
        H["📤 Output<br/>(256×new_seq 3D张量)"]::inputOutput

        A --> B
        B --> C
        C --> D
        D --> E
        E --> F
        F --> G
        G --> H
    end

    linkStyle 0 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 1 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 2 stroke:#1890ff,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 3 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 4 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 5 stroke:#4682B4,stroke-width:2px,arrowheadStyle:filled;
    linkStyle 6 stroke:#2F4F4F,stroke-width:2px,arrowheadStyle:filled;
