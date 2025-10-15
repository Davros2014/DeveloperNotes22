
A class should have single primary responsibility

	class Journal {
		constructor() {
		 	this.entries = {};
		}
	addEntry(text) {
			let c = ++Journal.count;
			let entry = `${c}: ${text}`;
			this.entries[c] = entry;
			return c;
		}
	} 
	Journal.count = 0;
