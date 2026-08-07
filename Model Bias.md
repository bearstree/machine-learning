$\color{red}{\text{Model Bias}}$  
Bias observed in a machine-learning model can come from several places. The main idea is that bias may be introduced anywhere along the pipeline:  
**Data**→**Labels**→**Features**→**Model**→**Training**→**Deployment**  

Common sources include:  
&emsp; **Sampling bias**: the training data is not representative of the population where the model will be used. For example, a medical model trained mostly on younger patients may perform worse on older patients.  
&emsp; **Historical bias**: the data accurately reflects past decisions or social patterns, but those historical patterns themselves are biased.  
&emsp; **Measurement bias**: variables are measured differently or with different accuracy across groups. Sensor quality, survey design, or data-collection procedures can introduce this.  
&emsp; **Label bias**: the target labels are inaccurate or systematically biased. For example, using historical hiring decisions as the ground-truth label may reproduce biases in previous hiring.  
&emsp; **Annotation bias**: human annotators may interpret examples differently because of subjective judgment, cultural background, or unclear annotation rules.  
&emsp; **Feature-selection bias**: important variables may be omitted, or chosen features may act as proxies for sensitive attributes. For instance, ZIP code can sometimes indirectly encode socioeconomic or demographic information.   
&emsp; **Model/inductive bias**: every model makes assumptions. A linear model, for example, assumes relationships that can be represented approximately linearly. If the true relationship is more complex, the model can systematically underfit.  
&emsp; **Objective-function bias**: the loss function optimizes what you specify, not necessarily what you actually care about. Optimizing overall accuracy on an imbalanced dataset, for example, may sacrifice performance on a minority class.  
&emsp; **Class imbalance**: if one group or class is much more common, training can be dominated by that group, causing systematically worse predictions for underrepresented examples.  
&emsp; **Optimization or regularization effects**: strong regularization, insufficient training, poor hyperparameters, or optimization constraints can cause systematic underfitting.  
&emsp; **Distribution shift**: the deployment population differs from the training population. Even an initially unbiased model may behave systematically incorrectly after the environment changes.  
&emsp; **Feedback-loop bias**: model predictions influence future data. For example, if a fraud model investigates certain customers more often, more fraud may be discovered in that group, reinforcing the model's original pattern.  

Model bias can originate from biased or unrepresentative training data, biased labels or measurements, inapporpriate feature selection, assumptions imposed by the model architecture, the training objective or loss function, class imbalance,
and distribution changes after deployment. Is is therefore important to diagnose whether the bias originates from the data-generating process, the learning algorithm, or the way the model is evaluated and deployed.  

Also distinguish this from the bias in the bias–variance tradeoff. In that context, “high bias” specifically means systematic error caused by an overly restrictive model or underfitting—for example, fitting a linear model to a strongly nonlinear relationship.
