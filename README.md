## Checkpoint

https://github.com/user-attachments/assets/e5922041-c856-4095-a99a-138ef87f6f33

## Créer un livre avec stock connu
<img width="1740" height="652" alt="image" src="https://github.com/user-attachments/assets/55301080-6781-4612-b60d-20970c9b326c" />

<img width="1745" height="704" alt="image" src="https://github.com/user-attachments/assets/0482e485-2293-4032-b88b-c1a361900a00" />

## Tester borrow une fois (sans concurrence):
<img width="1727" height="527" alt="image" src="https://github.com/user-attachments/assets/9c639289-74e1-4dc6-8203-638a4ee359ac" />

## Rendre loadtest.sh exécutable + Lancer le test:
<img width="1919" height="1013" alt="image" src="https://github.com/user-attachments/assets/b34d7520-4f99-45ad-ae4c-0249f0752a1f" />

<img width="1919" height="1003" alt="image" src="https://github.com/user-attachments/assets/a16df450-c9e3-4022-bf5d-ae451192c292" />

## Lire l’état du stock final
<img width="1721" height="704" alt="image" src="https://github.com/user-attachments/assets/8bd8ae8d-c429-45cc-918a-ed69ca2060ea" />

## Stop pricing-service
<img width="1065" height="107" alt="image" src="https://github.com/user-attachments/assets/4bab7409-9dd7-4f2d-82b9-4151f6002594" />

## Créer un nouveau livre avec stock 10
<img width="1746" height="671" alt="image" src="https://github.com/user-attachments/assets/34b81ee9-3f4a-48a1-b913-818d3206d75f" />

<img width="1720" height="835" alt="image" src="https://github.com/user-attachments/assets/6ebabf40-f5cf-44a0-8fb7-096b33b4888a" />

<img width="1300" height="325" alt="image" src="https://github.com/user-attachments/assets/0f73196b-548f-4aed-9f8e-9cffedfa6231" />
## Conclusion

Le **verrou en base de données** (SELECT FOR UPDATE) est indispensable en architecture multi-instances car il garantit l'exclusion mutuelle au niveau du stockage partagé. Sans ce verrou, plusieurs instances pourraient lire simultanément le même stock disponible et créer des emprunts concurrents, violant ainsi les contraintes métier (overbooking). Le verrou sérialise les transactions critiques et assure la cohérence des données.

Le **circuit breaker** protège le système contre les défaillances en cascade en détectant les services défaillants et en "ouvrant le circuit" pour éviter des appels inutiles qui aggraveraient la situation. Le **fallback** complète cette protection en fournissant une réponse dégradée mais acceptable (données en cache, valeur par défaut) lorsque le service distant est indisponible, garantissant ainsi la résilience et une expérience utilisateur acceptable même en cas de panne partielle du système distribué.

https://github.com/user-attachments/assets/f0a64684-1071-44d9-8b41-e1d10a568333



