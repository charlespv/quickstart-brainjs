# Javascript ML

## Quickstart Brain js

Arborescence:
	
    - iris_brainjs (folder)
	- - server.js (file)


CLI

	npm init -y
	npm i -s brain.js


server.js (file)

	// Importer BrainJS
	const  Brain  =  require('brain.js');
	// Créer un réseau de neurones
	const  NeuralNetwork  =  new Brain.NeuralNetwork();
	// Afficher le réseau dans la console
	console.log(NeuralNetwork);


CLI

	npm start
	// OR
	node server.js


server.js (file)

	// Définir les données d'entraînement
    const trainingData = [
        { input: { age: 0.68, earning: 0.168, schooling: 0.19 }, output: { diligent: 1 } },
        { input: { age: 0.53, earning: 0.117, schooling: 0.16 }, output: { diligent: 0 } },
        { input: { age: 0.31, earning: 0.198, schooling: 0.12 }, output: { diligent: 0 } },
        { input: { age: 0.30, earning: 0.126, schooling: 0.13 }, output: { diligent: 0 } },
        { input: { age: 0.43, earning: 0.131, schooling: 0.13 }, output: { diligent: 0 } },
        { input: { age: 0.48, earning: 0.227, schooling: 0.21 }, output: { diligent: 1 } },
        { input: { age: 0.71, earning: 0.148, schooling: 0.18 }, output: { diligent: 1 } },
        { input: { age: 0.60, earning: 0.047, schooling: 0.19 }, output: { diligent: 0 } },
        { input: { age: 0.56, earning: 0.214, schooling: 0.18 }, output: { diligent: 1 } },
        { input: { age: 0.57, earning: 0.133, schooling: 0.16 }, output: { diligent: 1 } },
        { input: { age: 0.41, earning: 0.203, schooling: 0.09 }, output: { diligent: 0 } },
        { input: { age: 0.68, earning: 0.176, schooling: 0.17 }, output: { diligent: 1 } },
        { input: { age: 0.59, earning: 0.059, schooling: 0.10 }, output: { diligent: 0 } }
    ];


    // Définir les données de test
    const testData = [
        { age: 0.49, earning: 0.040, schooling: 0.11 }, // 0
        { age: 0.71, earning: 0.038, schooling: 0.09 }, // 0 => error
        { age: 0.58, earning: 0.058, schooling: 0.15 }, // 0
        { age: 0.75, earning: 0.093, schooling: 0.18 }, // 1
        { age: 0.61, earning: 0.160, schooling: 0.14 }, // 1
        { age: 0.46, earning: 0.169, schooling: 0.18 } // 1 => error
    ];	

	// ...
	
	// Train the network
	NeuralNetwork.train(trainingData);
	
	// Tester le réseau
	testData.forEach(item  =>  {

		// Test
		const  newData  =  NeuralNetwork.run(item);
		
		//Afficher le résultat dans la console
		console.log(newData);
	});


server.js (file)

	// Config du training

    const trainConfig = {
        errorTresh: 0.001, // Niveau de training
        iterations: 30000, // Nombre de boucle pour le training
        log:true, // Affichage de compte rendus(log) pendant le training
        logPeriod: 100, // Durée de la periode (en fonction itérations) entre chaque log
    }

    // ...

    // Train the network
    NeuralNetwork.train(trainingData, trainConfig); 





