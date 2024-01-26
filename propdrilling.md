## propDrilling 
it is just passing down the state as prop from the outer most function to inner where it is needed
even if most of the function in between the functions donot need those.
So it makes the syntax bad that is the only drawback 
but when we use that prop in unneccessary function just for passing it donot rerender them so we should not be confused.

problem fixed using what called context API

## Context API
basically teleporting of the state down to the function that needs

`${export const CountContext = createContext(0);}`

## Context_API-Provider

any function that needs the state variable should be wraped inside the provider that is provided by the react as it is its component 

const [count, setCount] = useState(0);

`${
    <CountContext.Provider value = {count}>
        <Count  setCount = {setCount}/>
    </CountContext.Provider>
    
    `${ <CountContext.Provider value = {count}>
            <One setCount = {setCount}/>
        </CountContext.Provider>}`
    
}`

function Count(){
return (
<>
<CountRenderer/>
</>
)
}

function CountRenderer({count}){
const count = useContext(CountContext)

return (
<>
{count}
</>

)

}

function one(){
    return (
<>
    <two/>
    <three/>
    <four/>

</>
)
}

function four(){
return(
<>
hello
</>
)
}

function two(){
    
    const count = useContext(CountContext)

    return(
        <>
            {count}
        </>
    )
}

function four(){

    const count = useContext(CountContext)
    return (
        <>
        <button onClick = (count)=>{setCount(count + 1)}> increase </button>
        </>
    )
}