/* promise in javaSript is a way to handle task that takes time to get complete like
loading/fetching data from server and reding file etc. simply it deals with the asynchronus task/operations that
won't happens instantly but you still want to keep track there promise comes.
promise has 3 state 
pending = not completed but in pending state waiting for result / task is in progress
resolve/fulfilled = result has comed / task completed
reject = didn't meet condition or some error / task failed

Asynchronus = it won't wait for this promise to be resolve or reject it will do other task or complete
              other task and when teh 1st task is completed of promise then it will call and then provides result.
              meaning it won't stop it keep checking or completing other task in the program and when the result or 
              responce comes from the promise it will go to promise and call the promise responce.
              ensuring program to run faster and efficient

              example is given in line no 64 at last of the code  */


const promise1= new Promise(function(resolve,reject){ //new keyword create always instance of object that has constructor function
    const check=8090;
    if(check===8080){
        resolve("1st task complete"); //if the condition meets resolve 
    }
    else{
        reject("error"); //doesn't meet reject
    }
})

promise1.then(response=> { //then block always give the resolve value acc to condition 
    console.log(response);
    return response + " as well as 2nd";
})
.then((Resp2)=>{ //chaining resolve block if more response or information is needed to send the we can chain like this as much we need
    console.log(Resp2);
    return Resp2+ "  as well as 3rd";
})
.then(res3rd=>{ 
    console.log(res3rd)
})                                   //we can chain the catch block also as per need 
.catch(error=> console.log(error)) // when condtion fails  it will throw catch block acc to what message you are throwing as error
.finally(lastSatge=> console.log("i will always run and i run when all promises get consumed or all the task get completed"));


// this was the base example for promise 



//another example keeping delays in program like real problems

let promCheck=3000;
const promise2= new Promise((resolve,reject)=>{
    setTimeout(()=>{  //setTimeout take two arguments 1 is function and time as per you need to delay
        if(promCheck===3000){
            resolve('1st task complete');
        }
        else{
        reject("something went wrong");
        }
    },5000) // i'm keeping here 5 sec delay
   
})


promise2.then((response)=>{
    console.log(response);
})
.catch((error)=>{
    console.log(error);
})

console.log("My name is abi chhetri");   /* this is the example of asynchronus programming as the line is at the last in the program but
                                            it is running/executing before the promise1 and 2 because it is aynchronus and asynchronus mean 
                                            i have defined it in line no 4 */
