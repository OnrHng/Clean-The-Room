# Clean-The-Room
filtering same value in array and made a group them. and also check in array number or string . after all of them create a new array and merge all group of same number,different number and strings

it made with ES7 ( #arrowFunction)

# Exercise: Javascript Logic
Clean the room function: given an input of [1,2,4,591,392,391,2,5,10,2,1,1,1,20,20], make a function that organizes these into individual array that is ordered. For example answer(ArrayFromAbove) should return: [[1,1,1,1],[2,2,2], 4,5,10,[20,20], 391, 392,591]. Bonus: Make it so it organizes strings differently from number types. i.e. [1, "2", "3", 2] should return [[1,2], ["2", "3"]]

and you r gonna find the below that i explained line by line with comment for you helping for understand

    const sameValue = [];//for same items in array
    const difValue = [];//for different items in array
    const newArray = [];//for new array after grouping items
    let temporaryArr=[];//temporary array for numbers
    let stringInArray=[];// array for strings
    function clean(arr){
        const sortArr = arr.slice().sort();
        console.log(sortArr);//look at how seen array after than sort()method
        sortArr.map( function (item , i) {// makes loop ever item in array
            if(sortArr[i+1] === item){// check it out item is same next item
                temporaryArr.push(item);//if yes, write it on temporary array
                console.log('after item check' , temporaryArr)//look at temporary array how is seen
            }
            else if (item === sortArr[i-1]) {//chechk it out item is same previous item
                temporaryArr.push(item);//if yes, than write it on temporary array again
                console.log(temporaryArr);//look at temporary array how is seen
                sameValue.push(temporaryArr);//
                console.log('previous item check' , sameValue)//look at how seen sameValue array
                temporaryArr=[];
            }
            else if ( typeof item == 'string' ) {
                stringInArray.push(item);// if item is string than write it on string array
                console.log('string array' , stringInArray)// look at that how seen different Value array
            }
            else {
                difValue.push(item);// otherweise item is different next and also previous item 
                                    // than write it on different Value array
                console.log('different number' , difValue)// look at that how seen different Value array
            }
        });
        return newArray.concat([difValue] , [sameValue] , [stringInArray]);// merge sameValue array, Different Value array and Sting array
    }

    clean([1,2,4,591,392,391,2,5,10,2,1,1,1,20,20,'4','7','onur','ztm']);
