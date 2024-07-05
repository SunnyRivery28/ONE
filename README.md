// El desafío de este código era hacer posible que el usuario pueda modificar el rango de elección del juego del "Número secreto"

alert('Bienvenidos al juego del número secreto');
let numeroUsuario = 0;
let numeroLimite = 0;
let numeroSecreto =0;
console.log(numeroSecreto);
let intentos = 1;
let maxIntentos = 5;


do{

    numeroLimite = parseInt(prompt(`Por favor ingresa hasta que número límite quieres adivinar, ¿Hasta 10 , 100 o 1000? ¡El que quieras! Pero recuerda, sólo tienes ${maxIntentos} intentos.`));
    console.log(numeroLimite);

    if (numeroLimite <= maxIntentos) {
        alert('Vamos... No hagas trampa, inserta otro número.'); 
    } else {
        numeroSecreto = Math.floor(Math.random()*numeroLimite+1);
        console.log(numeroSecreto);
        break;
    }

} while (numeroLimite < maxIntentos );
console.log('Resultado de la comparación:', numeroUsuario == numeroSecreto);

while (numeroUsuario != numeroSecreto) {

    numeroUsuario = parseInt(prompt(`Elige un número entre 1 y ${numeroLimite} por favor`));
    console.log(typeof(numeroUsuario));

    if (numeroUsuario == numeroSecreto) {
        alert(`Acertaste, el número es: ${numeroUsuario} lo lograste en ${intentos} ${intentos == 1?'vez':'veces'}.`); 
    } else {
        console.log(numeroSecreto);
        if (numeroUsuario > numeroSecreto) {
            alert('El número secreto es menor');
        } else {
            alert('El número secreto es mayor');
        }
        
        // Aumentamos el contador en el else.
        intentos++;
        if (intentos > maxIntentos) {
        alert(`Llegaste al número máximo de ${maxIntentos} intentos.`)
        break;
        }
    }
   
}
