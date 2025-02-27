
E5 - Ground Shaking and Liquefaction
====================================

+-----------------+-----------------------------------------------------------------+
| Download files  | :examplesgithub:`Download <E5GroundShakingAndLiquefaction/>`    |
+-----------------+-----------------------------------------------------------------+

This example presents a coupled damage assessment for ground shaking and liquefaction hazards. To infer liquefaction, estimates of horizontal spreading and vertical settlement are generated from PGA values obtained through PSHA. These three intensity measures form the basis of input to a building-level, HAZUS-based damage and loss assessment that accounts for potential collapses due to liquefaction. Approximately 14,000 buildings are considered in the city of Alameda, CA.

.. figure:: r2dt-0005.png
   :width: 400px
   :align: center

#. **VIZ** This example shows a simulation for pseudo-earthquake scenarios. The damage and loss of a sample of buildings in Alameda County due to the soil liquefaction are estimated.  The results presented herein are only for demonstrating the use of R2DTool and do not serve as an accurate representation of the real losses.

   .. figure:: figures/r2dt-0005-VIZ.png
      :width: 600px
      :align: center


#. **GI** Next, the general information panel is used to broadly characterize the problem at hand. In this example, the imperial force and length units are used, and we're interested in the engineering demand parameters, damage measures, and the resulting decision variable (e.g., expected replacement cost).

   .. figure:: figures/r2dt-0005-GI.png
      :width: 600px
      :align: center


#. **HAZ** Now in the hazard panel, the **User Specified Ground Motions** option is selected which allows for the use of pre-generated earthquake scenarios. The following figure shows the relevant example files which are now entered in this pane. The peak ground acceleration and peak ground deformation (in both the horizontal and vertical directions) are used as intensity measures to quantify the potential earthquake effects.

   .. figure:: figures/r2dt-0005-HAZ.png
      :width: 600px
      :align: center


#. **ASD** In the asset definition panel, the path to the ``all_bldgs.csv`` file is specified. Once this file is loaded, the user can select which particular assets will be included in the analysis by entering a valid range in the form and clicking **Select**. For this example, the range **1-20** is used to include all buildings. The ``input_params.csv`` includes parameters for the damage and loss assessment (i.e., number of stories, year of built, occupancy class, structure type, plan area, replacement cost, population, and soil type).

   .. figure:: figures/r2dt-0005-ASD.png
      :width: 600px
      :align: center

#. **HTA** Next, a hazard mapping algorithm is specified using the **Nearest Neighbor** method and the **SimCenterEvent** application, which are configured as shown in the following figure with **1000** samples in **4** neighbors.

   .. figure:: figures/r2dt-0005-HTA.png
      :width: 600px
      :align: center

#. **MOD** In the building modeling panel, simply leave the first dropdown box set to **None**.

   .. figure:: figures/r2dt-0005-MOD.png
      :width: 600px
      :align: center
	  
#. **ANA** In the analysis panel, **IMasEDP** is selected from the primary dropdown.

   .. figure:: figures/r2dt-0005-ANA.png
      :width: 600px
      :align: center

#. **DL** The damage and loss panel is now used to configure the **Pelicun3** backend. The **HAZUS MH EQ IM** damage and loss method is selected and configured as shown in the following figure:

   .. figure:: figures/r2dt-0005-DL.png
      :width: 600px
      :align: center

#. **UQ** For this example the **UQ** dropdown box should be set to **None**.

   .. figure:: figures/r2dt-0005-UQ.png
      :width: 600px
      :align: center

#. **RV**

   The random variable panel will be left empty for this example.

#. **RES** The analysis outputs for the selected 10 buildings are shown in the figure below.

   .. figure:: figures/r2dt-0005-RES.png
      :width: 600px
      :align: center
