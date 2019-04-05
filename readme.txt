codigo de la pagina html  / esto para el tab2
---------------------------
<ion-header>
  <ion-toolbar>
    <ion-title>
      Hola Mundo
    </ion-title>
  </ion-toolbar>
</ion-header>

<ion-content>
  <!-- Item Labels -->
  <ion-card-content>

    <ion-item>
      <ion-avatar>
        <img src="assets/monkey2.jpg">
      </ion-avatar>
      <ion-label position="floating">Ingesa tu nombre</ion-label>
      <ion-input id="texto" type="text" [(ngModel)]="nombre"></ion-input>

    </ion-item>


    <ion-item>
      <ion-button expand="full" slot="end" (click)="llamarToast()">Dale!</ion-button>
    </ion-item>
  </ion-card-content>


</ion-content>

----------------------------------

codigo ts

--------------

import { Component } from '@angular/core';
import { AlertController, ToastController } from '@ionic/angular';

@Component({
  selector: 'app-tab2',
  templateUrl: 'tab2.page.html',
  styleUrls: ['tab2.page.scss']
})
export class Tab2Page {

  nombre :string;
  cuenta :boolean;
  constructor( public alertCtrl: AlertController,public toast : ToastController){

   
  }

  ionViewDidLoad() {
  console.log('ionViewDidLoad ');

    
}



async llamarToast() {
  const toast = await this.toast.create({
    message: 'hola '+ this.nombre,
    duration: 3000
  });
  toast.present();
}


}
