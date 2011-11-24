jSql aims to provide a set of sql-like methods to make the processing of large entities easy.

Some examples:

				var testArray = [1,2,3,4,5,6,7,8,9,10];

				jSql(testArray).skip(3).take(2); // an instance of jSql that holds [4, 5]

				jSql([1,2,3,4,5,6,67,7,89,9]).select("3 2").getElement(); // [4, 3]

				jSql(testArray).sum(); //55

				var arrOfObj = [{ name: "Nicolas" }, { name: "Florencia" }, { name: "Roberto" }, { name: "Juan" }, { name: "Nicolas" }];

				jSql(arrOfObj).select("name").where("0='Nicolas'||0='Florencia'").getElement() // ["Nicolas"]

				jSql(arrOfObj).select("name").whereAll("0='Nicolas'||0='Florencia'").getElement() // ["Nicolas", "Florencia", "Roberto", "Juan", "Nicolas"]

				jSql([1,2,3,1]).merge([1,2,3,1])  // [1, 2, 3, 1, 1, 2, 3, 1]
							   .distinct().getElement() // [1, 2, 3]