

	const func: (a: string, b: number, c: boolean) => void = (a, b, c) => 


Void mean the function returns nothing, this value would be the resultant value the function returns. ie string, number, boolean

### **Typing objects**

"type" and "interface" are similar but an interface is extensable

### **Interface**

	interface ISearchProps {  
	  className: string;  
	  placeholder: string;  
	  type: string;  
	  value: string;  
	  onChangeHandler: (a: string) => void  
	}

**The following could be written as follows where ISearchProps extends the values of IchangeHandlerProps**

**Note: ALL interface names start with an I**

	interface ISearchProps extends IchangeHandlerProps {  
	  className: string;  
	  placeholder: string;  
	  type: string;  
	  value: string;  
	}  
	
	interface IchangeHandlerProps {  
	  onChangeHandler: (a: string) => void  
	}  

	const searchbox =({className, placeholder, type, value, onChangeHandler}: ISearchProps) => {...}

### **Type**

**Note: Type names are not required to start with an I**

	type SearchBoxProps = {  
	    className: string;  
	    placeholder: string;  
	    onChangeHandler: (a: string) => void  
	}

### **Types allow us to do a UNION**

	type CanadianAddress = {  
	    street: string;  
	    province: string;  
	}
	
	type USAddress = {  
	    street: string;  
	    state: string;  
	}

The union would be done thusly;

	type NorthAmericanAddress = CanadianAddress | USAddress  

	const NorthAmericanAddress = {  
	  state: "kfhbf",  
	  street: "jeyggye"  
	}
	
	type ItalianAddress {  
	    street: string;  
	    region: string;  
	}

If we create the above it can also be added to the union

	type NorthAmericanAddress = CanadianAddress | USAddress | ItalianAddress
	
	const NorthAmericanAddress = {  
	  state: "kfhbf",  
	  region: "Toscana"  
	}