Παράλληλα και διανεμημένα  συστήματα  
Κουργιαντάκης Γεώργιος 8592 : https://github.com/Gekourgia/Parallel-and-Distributed-Systems  
Τσομλεκτσόγλου Βασίλειος 8259 : https://github.com/tsomilios/Parallel-Ergasia.git  

_Εργασία 1_

Αρχικα οι πρώτες μου ενέργειες για την δημιουργία του κώδικα ήταν η ανάγνωση των πολλών αρχείων
examples που που παρέχονταν για την βοήθεια μας. Τόσο ο πίνακας coo όσο και τα Market Matrix ήταν αναγκαία 
για να λυθούν τα προβλήματα που ζητήθηκαν.

Triangle_V3:
Για τον αλγόριθμο triangle_v3 χρησιμοποιήθηκαν οι συναρτήσεις από τα αρχεία mmio,read.mtx καθως το αρχείο coo2csc. 
Μέσω αυτών ων αρχείων δίνεται η δυνατότητα μέσω του terminal να επιλέξει ο χρήστης 0,1 για μη δυαδικό και δυαδικό πίνακα αντίστοιχα. 
Στο συγκεκριμένο ερώτημα για να μην γίνονται πολλαπλές καταμετρήσεις των ιδίων τρίγωνων μετατρέπεται ο πίνακας σε άνω ή κάτω τριγωνικός. 
Αφού μετατραπεί o πίνακας από coo σε csc μορφή μπορεί να ξεκινήσει η αναζήτηση η οποία θα συμβαίνει ανά στήλη βρίσκοντας τις 
μη μηδενικές γραμμές. Αφού τις βρει παίρνει τις συντεταγμένες οι οποίες είναι η πρώτη κορυφή τρίγωνου.
Αφού οι πίνακες είναι συμμετρικοί ισχύει ότι (row=col) , ψάχνω σε ποια άλλη στήλη έχω το row1.Και παίρνω την επόμενη κορυφή (col2 ,row1).
Tέλος ελέγχω την 3 κορυφή η οποία είναι (col1, col2) και αν και αυτή περιέχει μη μηδενική τιμή αυξάνω τον αριθμό των τρίγωνων και τον πίνακα c3 με της ανάλογες κορυφές.

Triangle_v3_cilk Για την υλοποίηση του Cilk στην v3  χρησιμοποίησα παραλληλισμό στο εξωτερικό for  loop.

Triangle_v3_openmp: Ομοίως έπραξα και για το Open MP με χρήση του pragma omp.

Triangle_V4:
Για τον κώδικα του v4  έγινε χρίση των οδηγιών της 3 παραγράφου και του πολλαπλασιασμού στο σημείο για τους πίνακες C=A⊙(AA). Ουσιαστικά ένα κομμάτι του κώδικα παραμένει ίδιο με το v3 και χρησιμοποιούνται οι συντεταγμένες των μη μηδενικών τιμών ώστε να βρεθεί το πλήθος των τρίγωνων. 

Triangle_v4_calk: Με χρίση του cilk_for παραλληλοποιηθηκε το εξωτερικό  loop και στην συνέχεια και το εσωτερικό . Αυτό έδειξε κάποια διαφορά στους χρόνους χωρίς όμως κάτι το σημαντικό.’

Triangle_v4_openmp: Με χρήση του pragma  στο εξωτερικό loop κυρίως παρατηρήθηκαν μικρές διάφορες. 

Triangle_v4_pthreads: Για την υλοποίηση των pthreads σκοπός και πάλι ήταν η παραλληλοποιηση του for loop σε κομμάτια. Δηλαδή κάθε worker αναλάμβανε από ένα κομμάτι. Βέβαια κάτι τέτοιο αποδείχθηκε να μην λειτουργεί πλήρως καθώς οι αποδόσεις σε χρόνο έδειχναν όλο και να μεγαλώνουν. Αρά με την αύξηση των workers αργούσε όλο και περισσότερο.

Σχόλια:
Σε γενικές γραμμές φάνηκε πως ο triangle_v3 ήταν γρηγορότερος από τον v4 πράγμα που βέβαια μπορεί αν οφείλεται στην υλοποίηση και μια διαφορετική να έδειχνε καλυτέρα αποτελέσματα.
Επίσης περίεργο ήταν στην threads που ο μεγαλύτερος αριθμός worker φαίνεται να αύξανε την διάρκεια εκτέλεσης της εργασίας. Ίσως προβληματικό ήταν και το σημείο από το οποίο ξεκινούσε να μετράει χρόνο το πρόγραμμα.


Τα διαγραμματα ειναι ορατα μεσα στο φακελο report στο αρχειο pdf με ιδιο ονομα.




 

 

 

 

 


 

 


 





