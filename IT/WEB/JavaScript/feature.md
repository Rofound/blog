# The JavaScript Feature?

- reference transfer(The variable just a reference in below function)
	- setTimeout
			
			for(var i = 0; i < 3; i++){
				setTimeout(function(){
					console.info(i); // will be print 3 times
					/*
						Why?
						Because the i's value is 3 at last!
						Just a reference, my friend.
					*/
				},1000);
			}

			
	- addEventListener(The variable just a reference in below function)
	
			<button>一</button>
			<button>二</button>
			<button>三</button>
			<button>四</button>
			<button></button>
			
			var tsts = document.querySelectorAll("BUTTON");
			for(var i = 0, tstsLength = tsts.length; i < tstsLength; i++){
				tsts[i].addEventListener("click", function(){
					tsts[tstsLength - 1].innerText = tsts[i].innerText; //will tip error, the tsts[i]'s addEventListener is not a function!
					/*
						Why?
						Because the i's value is 3 at last!
						Just a reference, my friend.
					*/
				}, 2000);
			}

- reference transferat solution
	- variable copy(Nothing)
	- closure()
	- anonymous function(ES6 good)

- closure
	- 