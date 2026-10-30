# Physics Lib

Biblioteca educacional em **C++17** que reúne funções para cálculos de Física introdutória. O projeto organiza as implementações por área de estudo e disponibiliza constantes reutilizáveis para apoiar exercícios e aplicações acadêmicas.

## Módulos implementados

### Cinemática

Funções para cálculos relacionados ao movimento:

- Velocidade média: `calculateAverageVelocity()`
- Posição no movimento uniforme: `calculateUniformMotionPosition()`
- Aceleração média: `calculateAverageAcceleration()`
- Velocidade final em função do tempo: `calculateFinalVelocityFromTime()`
- Posição no movimento uniformemente variado: `calculateUniformlyVariedMotionPosition()`
- Velocidade final pela equação de Torricelli: `calculateFinalVelocityFromDisplacement()`

### Dinâmica

Funções para cálculos de força e movimento:

- Força resultante: `calculateForce()`
- Aceleração: `calculateAcceleration()`
- Peso: `calculateWeight()`
- Força de atrito: `calculateFrictionForce()`

### Energia

Funções relacionadas a energia e trabalho:

- Energia cinética: `calculateKineticEnergy()`
- Energia potencial gravitacional: `calculateGravitationalPotentialEnergy()`
- Energia mecânica total: `calculateTotalMechanicalEnergy()`
- Trabalho mecânico: `calculateWork()`
- Potência: `calculatePower()`
- Energia potencial elástica: `calculateElasticPotentialEnergy()`
- Variação da energia cinética: `calculateWorkFromKineticEnergyVariation()`

## Constantes disponíveis

O namespace `physics::constants` reúne constantes utilizadas pelos módulos:

| Nome | Descrição |
|---|---|
| `kPi` | Constante matemática π. |
| `kEarthGravity` | Valor de referência da gravidade terrestre: 9,8 m/s². |

Exemplo:

~~~cpp
#include "constants.h"

double angleRadians =
    90.0 * physics::constants::kPi / 180.0;

double weight =
    mass * physics::constants::kEarthGravity;
~~~

## Exemplo de uso

~~~cpp
#include <iostream>
#include "dynamics.h"

int main()
{
    const double mass = 10.0;
    const double acceleration = 5.0;

    const double force =
        physics::dynamics::calculateForce(
            mass,
            acceleration
        );

    std::cout << "Força: " << force << " N\n";
    return 0;
}
~~~

Saída esperada para os valores do exemplo:

~~~text
Força: 50 N
~~~

## Tecnologias e ferramentas

- C++17
- CMake 3.16 ou superior
- Documentação de código com Doxygen

## Compilação

É necessário ter um compilador com suporte a C++17 e o CMake instalado.

~~~bash
cmake -S . -B build
cmake --build build
~~~

O projeto configura um executável de demonstração. Em sistemas nos quais o executável gerado se chama `app`, ele pode ser iniciado com:

~~~bash
./build/app
~~~

## Organização

~~~text
physics-lib/
├── include/
│   ├── constants.h
│   ├── dynamics.h
│   ├── energy.h
│   └── kinematics.h
├── src/
│   ├── dynamics.cpp
│   ├── energy.cpp
│   ├── kinematics.cpp
│   └── main.cpp
├── CMakeLists.txt
└── README.md
~~~

## Escopo atual

A implementação está concentrada em Cinemática, Dinâmica e Energia. Tópicos como quantidade de movimento, Termodinâmica, Eletromagnetismo e Gravitação Universal são possibilidades de expansão, não módulos documentados como concluídos.

O objetivo é oferecer implementações simples e organizadas para estudo de Física e prática de C++ moderno.