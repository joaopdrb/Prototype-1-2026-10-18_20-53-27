# Prototype 1 — Simulação de Direção em Unity

Protótipo jogável em 3D desenvolvido na **Unity** durante o curso oficial [**Create with Code**](https://learn.unity.com/course/create-with-code?version=6.0), da Unity Learn. O projeto corresponde à **Unidade 1 — Player Control** e aplica os fundamentos de C# e do editor da Unity: um veículo controlado pelo teclado percorre uma estrada, com uma câmera que o acompanha e caixas espalhadas pelo cenário.

![Unity](https://img.shields.io/badge/Unity-6000.3-black?logo=unity)
![C#](https://img.shields.io/badge/C%23-239120?logo=csharp&logoColor=white)
![Render Pipeline](https://img.shields.io/badge/URP-17.3-blue)
![Input System](https://img.shields.io/badge/Input%20System-1.20-orange)

<!-- Adicione aqui uma captura de tela ou GIF do jogo, por exemplo: ![Gameplay](docs/gameplay.gif) -->

## O que o projeto faz

- Controla um veículo (picape vermelha) com **aceleração, ré e giro** a partir do teclado.
- Mantém uma **câmera em terceira pessoa** que segue o veículo a uma distância fixa.
- Monta um cenário com **estrada**, **céu em domo**, **skybox de montanhas** e **7 caixas** posicionadas na pista.

## Controles

| Ação | Teclas |
|---|---|
| Acelerar / ré | `W` / `S` ou `↑` / `↓` |
| Virar à esquerda / direita | `A` / `D` ou `←` / `→` |

## Destaques técnicos

O comportamento do jogo está em dois scripts em `Assets/Scripts/`:

**`PlayerController.cs`** — movimento do veículo
- Usa o **novo Input System** da Unity: uma `InputAction` do tipo `Vector2`, exposta no Inspector, com dois composites 2D (WASD e setas).
- Desloca o veículo no eixo local Z com `Transform.Translate()` e o gira no eixo Y com `Transform.Rotate()`.
- Multiplica o movimento por `Time.deltaTime` para que a velocidade independa da taxa de quadros.
- `speed` e `turnSpeed` são variáveis públicas ajustáveis no Inspector (valores na cena: `25` e `70`).

**`FollowPlayer.cs`** — câmera de acompanhamento
- Atualiza a posição da câmera em `LateUpdate()`, depois do movimento do veículo, para evitar tremor.
- Mantém um deslocamento fixo em relação ao jogador (`0, 5, -7`).

## Tecnologias

| Item | Versão |
|---|---|
| Unity Editor | 6000.3.26f1 (Unity 6.3) |
| Universal Render Pipeline (URP) | 17.3.0 |
| Input System | 1.20.0 |
| Linguagem | C# |

## Como executar

### Pré-requisitos

- [Unity Hub](https://unity.com/download)
- Unity Editor **6000.3.26f1** (o Unity Hub oferece a instalação ao abrir o projeto)

### Passos

1. Clone o repositório:
   ```bash
   git clone https://github.com/joaopdrb/Prototype-1-2026-10-18_20-53-27.git
   ```
2. No Unity Hub, clique em **Add → Add project from disk** e selecione a pasta clonada.
3. Abra o projeto e, em `Assets/Scenes/`, abra a cena **`Prototype 1`**.
4. Clique em **Play**.

> A cena `SampleScene` é a cena vazia do template. O protótipo está em `Prototype 1`.

## Estrutura do projeto

```
├── Assets/
│   ├── Scenes/
│   │   └── Prototype 1.unity     # Cena do protótipo
│   ├── Scripts/
│   │   ├── PlayerController.cs   # Movimento do veículo
│   │   └── FollowPlayer.cs       # Câmera de acompanhamento
│   ├── Course Library/           # Assets do curso (veículos, obstáculos, estrada, céu)
│   └── InputSystem_Actions.inputactions
├── Packages/
└── ProjectSettings/
```

## O que aprendi

- Montar uma cena na Unity: hierarquia de GameObjects, Prefabs, iluminação e câmera.
- Escrever scripts `MonoBehaviour` e usar o ciclo de vida da Unity (`Start`, `Update`, `LateUpdate`).
- Ler entradas do teclado com o novo Input System e transformá-las em movimento.
- Manter o movimento consistente entre máquinas com `Time.deltaTime`.
- Versionar um projeto Unity com Git e publicá-lo no GitHub.

## Possíveis evoluções

- Detectar colisões com as caixas e dar feedback visual e sonoro.
- Adicionar pontuação e condições de fim de jogo.
- Criar menu inicial e tela de reinício.

## Créditos e licença dos assets

Projeto educacional baseado no curso **Create with Code**, da Unity Technologies. Os modelos 3D da pasta `Course Library` foram fornecidos pela **Synty Studios** e **não podem ser usados comercialmente**. Para uso comercial, adquira os pacotes na [página da Synty Studios na Asset Store](https://assetstore.unity.com/publishers/5217). Este repositório tem finalidade exclusivamente de estudo e portfólio.

## Autor

**João Pedro** — advogado e desenvolvedor, com pós-graduação em Engenharia de Software.

GitHub: [@joaopdrb](https://github.com/joaopdrb)
