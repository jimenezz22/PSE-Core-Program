# Modulo 0

https://github.com/privacy-scaling-explorations/core-program/blob/main/2024/week0_course_primer.md

## Qué es ZK

Son protocolos de pruebas de conocimiento cero. En criptografía, una prueba de conocimiento cero (ZKPs) permite a una parte (el probador) demostrarle a otra parte (el verificador) que una declaración es verdadera sin revelar ninguna información adicional más allá de la veracidad de la declaración misma.

## Principios de ZKPs

Para que una prueba sea considerada de conocimiento cero, debe cumplir con las siguientes propiedades:

1. **Integridad (Completeness)**: Si la afirmación es verdadera, el prover puede convencer al verifier de que es cierto.
2. **Solidez (Soundness)**: Si la afirmación es falsa, ningún prover deshonesto puede convencer al verifier de que es cierto, excepto con una probabilidad muy baja.
3. **Conocimiento Cero (Zero-Knowledge)**: Si la afirmación es verdadera, el verifier no aprende nada más allá de la veracidad de la afirmación. No obtiene ninguna información adicional sobre el secreto o el dato subyacente.

## Tipos de ZKPs

1. **Pruebas Interactivas**: Estas requieren una interacción entre el prover y el verifier. Un ejemplo clásico es el protocolo de Feige-Fiat-Shamir.
2. **Pruebas No Interactivas (NIZK)**: Estas no requieren interacción y suelen utilizarse en escenarios donde la interacción no es práctica. Un ejemplo importante es el esquema zk-SNARK (Succinct Non-interactive Argument of Knowledge).
    
    ### Feige-Fiat-Shamir
    
    El protocolo de Feige-Fiat-Shamir es, de hecho, un tipo de prueba de conocimiento cero. Se ajusta a los mismos principios básicos que las pruebas de conocimiento cero, donde el demostrador puede probar la veracidad de una afirmación (en este caso, su identidad o conocimiento de un secreto) sin revelar ninguna información adicional sobre el secreto mismo. Por lo tanto, se puede considerar como una prueba de conocimiento cero tradicional.
    
    ### ZK-SNARK (Zero-Knowledge Succinct Non-Interactive Argument of Knowledge)
    
    Las zk-SNARKs son cruciales para mejorar la privacidad y escalabilidad de las transacciones.
    
    zk-SNARKs son un tipo específico de prueba de conocimiento cero que es conciso (succinct) y no interactivo (non-interactive). Esto significa que la prueba puede ser verificada rápidamente y no requiere múltiples interacciones entre el probador y el verificador.
    
    **En Ethereum:** Con la introducción de zk-rollups, se pueden agrupar múltiples transacciones en una sola prueba zk-SNARK, mejorando la escalabilidad y manteniendo la privacidad.
    
    ### STARKs **S**calable, **T**ransparent **AR**gument of **K**nowledge → Starknet
    
    son una tecnología criptográfica desarrollada por STARKWARE e implementadas en Starknet.  Se utilizan para crear pruebas de conocimiento cero que son escalables y transparentes, dichas pruebas permiten probar y verificar cálculos de forma eficiente y segura.
    
    ### ¿Cómo funcionan los STARKs?
    
    1. **Cálculos Fuera de la Cadena (Offchain)**: Grandes cantidades de cálculos se realizan fuera de la cadena principal de Ethereum, lo que es más barato.
    2. **Generación de Pruebas**: Se genera una prueba que valida que estos cálculos son correctos.
    3. **Verificación en la Cadena (Onchain)**: Solo la verificación de esta prueba, que es mucho más rápida y barata, se realiza en la cadena principal.
    
    ### Características Principales de STARKs:
    
    1. **Escalabilidad**: Los STARKs son diseñados para ser altamente escalables, lo que permite procesar grandes volúmenes de datos y transacciones de manera eficiente
    2. **Transparencia**: A diferencia de otros métodos de pruebas de conocimiento cero, como los zk-SNARKs, los STARKs no requieren un proceso de configuración confiable (trusted setup). Esto mejora la transparencia y la seguridad, ya que no se depende de una configuración inicial que podría ser vulnerable.
    
    ### Beneficios para Blockchain
    
    - **Mayor Escalabilidad**: Permiten procesar muchas más transacciones por segundo (TPS).
    - **Costos Reducidos**: Hacer cálculos offchain y solo verificar onchain reduce significativamente las tarifas.
    - **Seguridad de Ethereum**: Las transacciones mantienen la seguridad de Ethereum.
    
    ### Porqué las transacciones son más baratas usando STARKs:
    
    ### 1. **Agrupación de Transacciones (Batching)**
    
    En StarkNet, múltiples transacciones se agrupan en una sola prueba de conocimiento cero (en este caso, una prueba STARK). Esta prueba se verifica en la cadena principal de Ethereum, lo que significa que en lugar de pagar por cada transacción individualmente, se paga una tarifa combinada por verificar la prueba que agrupa muchas transacciones. Esto reduce significativamente el costo por transacción.
    
    ### 2. **Compresión de Datos**
    
    Las pruebas STARK permiten una compresión eficiente de datos. La cantidad de datos que necesita ser almacenada y procesada en la cadena principal de Ethereum es mucho menor, ya que solo se incluye la prueba en lugar de todas las transacciones individuales. Menos datos significa menos costos.
    
    ### 3. **Optimización Computacional**
    
    Las operaciones computacionales intensivas se realizan fuera de la cadena principal, en la capa dos (StarkNet). Solo el resultado final (la prueba STARK) se envía a la cadena principal. Esto alivia la carga de trabajo de la red principal de Ethereum y reduce las tarifas de gas asociadas con la ejecución de contratos inteligentes y procesamiento de transacciones.
    
    ### 4. **Descongestión de la Red Principal**
    
    Al mover un gran volumen de transacciones a la capa dos, la congestión en la red principal de Ethereum disminuye. Menos congestión significa que las tarifas de gas pueden bajar, ya que la demanda por espacio en los bloques de la cadena principal se reduce.
    
    ### 5. **Eficiencia de Escala**
    
    StarkNet puede manejar miles de transacciones por segundo debido a la naturaleza escalable de las pruebas STARK. Al tener una mayor capacidad para procesar transacciones, los costos por transacción se distribuyen de manera más eficiente entre los usuarios.
    
    ### Resumen
    
    Mover las transacciones a StarkNet reduce significativamente las tarifas de gas porque:
    
    - Se agrupan múltiples transacciones en una sola prueba.
    - Se comprimen los datos.
    - Las operaciones intensivas se realizan fuera de la cadena principal.
    - La red principal de Ethereum se descongestiona.
    - La mayor capacidad de procesamiento reduce los costos por transacción.

### What is Multi-Party Computation (MPC)

### Qué es Fully Homomorphic Encryption (FHE)