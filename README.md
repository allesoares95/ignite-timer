# Iniciando projeto 

`npm create vite@latest`

## dependencia 

`npm i `

## Utilizando CSS styled-components

`npm i styled-components`

`npm i @types/styled-components -D`

---

## utilização de estilos apenas com TypeScript 
  
  Sobre escrevendo tipagens de uma biblioteca existente 

  Tipagem de temas
    arquivo styles.d.ts;
    defaultTheme

# ESLint 

instalando como dependencia de desenvolvimento
` npm i eslint -D`

pacote da rocketseat ;
`npm i @rocketseat/eslint-config -D`

para testar e corrigir erros 
`npx eslint src --ext .ts,.tsx --fix`

para deixar automatizado o test crie um script no package.json em debug 
` "lint": "eslint src --ext .ts,.tsx --fix" `

para rodar ;
` npm run lint `

para fixar os erros 
` npm run lint --fix `

 * Caso queira ver as configurações utilizadas nesse plugin, você pode acessar o repositório oficial com o código dessas configurações para o React: https://github.com/Rocketseat/eslint-config-rocketseat/blob/main/react.js

 * O ESLint possui uma enorme lista de rules (regras) que você pode configurar, e todas estão disponíveis através desse link da documentação oficial: https://eslint.org/docs/rules/

 * Caso queira ver mais sobre como configurar o ESLint manualmente, você pode ver o guia de Getting Started do ESLint disponível no seguinte link: https://eslint.org/docs/user-guide/getting-started


# Lidando com varias rotas .

Utilizar react router dom 

` npm i react-router-dom `

conecatando componente Router com outras pages;

### Utilização de icons
`npm i phosphor-react `

### Biblioteca pra utilização de formularios
React Hook Form.
`npm install react-hook-form`

### Biblioteca de validação 
Zod ; https://github.com/colinhacks/zod

`npm i zod`

`npm i @hookform/resolvers`

### pacote para datas date-fns
`npm i date-fns`


## Utilização de Context API
-> Permite compartilharmos informações entre vários componentes ao mesmo tempo


Utilização de Contexto do activeCycle se for alterada no NewCycleForm era será 
altera em todos que estão utilizando o mesmo contexto;
Utilização sem propriedades nos componentes e mesmo assim eles consegue acessar 
uma informação do componente pai da Homepage;

```tsx
import { createContext, useContext, useState } from 'react'

const CyclesContext = createContext({} as any)

function NewCycleForm() {
  let { activeCycle, setActiveCycle } = useContext(CyclesContext)

  return (
    <h1>
      NewCycleForm: {activeCycle}
      <button
        onClick={() => {
          setActiveCycle = 2
        }}
      >
        Alterar ciclo ativo
      </button>
    </h1>
  )
}

function Countdown() {
  const { activeCycle } = useContext(CyclesContext)

  return <h1>Countdown: {activeCycle}</h1>
}

export function Home() {
  const [activeCycle, setActiveCycle] = useState(0)

  return (
    <CyclesContext.Provider value={{ activeCycle, setActiveCycle }}>
      <div>
        <NewCycleForm />
        <Countdown />
      </div>
    </CyclesContext.Provider>
  )
}
```


Utilização da biblioteca immerjs, para trabalhar com dados imutaveis ;
` npm i immer `