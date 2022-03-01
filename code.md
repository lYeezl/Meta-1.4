# Meta-1.4

servicioDatos.js

let finDeTransmisionDeDatos = function(id){

    console.log('Transferencia',id,'terminada');

}

let obtenDatosDeInternet= function(id, duracion){
    console.log('Proceso',id,'obteniendo datos de internet');
return new Promise((resolve,reject)=>{

    setTimeout(() =>{
    resolve(finDeTransmisionDeDatos);},id,duracion);
 } );
}

module.exports.getDatos = obtenDatosDeInternet;


clienteDatos.js
const servicio = require("./servicioDatos");

servicio.getDatos(1,300)
.then(()=>
    {servicio.getDatos(2,500)})
    .then(()=>{
        servicio.getDatos(3,4000)})
        .then(()=>{
            servicio.getDatos(4,700)})
            .then(()=>{ 
                servicio.getDatos(5,3500)})
                .catch((error) => {console.log(error);
                })    
