graph TD
    A[Input] --> B[Conv]
    B --> C[ReLU]
    C --> D[Aver-pooling]
    D --> E[ReLU]
    E --> F[Conv]
    F --> G[ReLU]
    G --> H[Output]
