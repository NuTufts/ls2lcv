
set( LARCV_LIB -L$ENV{LARCV_LIBDIR} -lLArCVCoreBase -lLArCVCoreDataFormat )
set( LARLITE_LIB -L$ENV{LARLITE_LIBDIR} -llarlite_Base -llarlite_DataFormat -llarlite_LArUtil)

include_directories ( $ENV{LARCV_BASEDIR} $ENV{LARLITE_BASEDIR} )

link_libraries( ${LIB_NAME} -L$ENV{BOOST_LIB} -lboost_system ${ROOTLIB} ${LARCV_LIB} ${LARLITE_LIB} ) # All execs need this.

art_make( EXCLUDE LLMetaMaker_service.cc
	  BASENAME_ONLY
	  LIBRARY_NAME ls2lcv_sbnd_LArCVMaker
	  LIB_LIBRARIES
	  	   larcorealg_Geometry
		   larcore_Geometry_Geometry_service
	   	   larsim_Simulation 
		   nug4::ParticleNavigation 
		   lardataobj_Simulation
		   larsim_MCCheater_ParticleInventoryService_service
		   lardataobj_RecoBase
		   nusimdata::SimulationBase
		   lardataobj_MCBase
		   larcoreobj_SummaryData
		   lardataobj_RawData
		   lardata_RecoObjects
		   nusimdata::SimulationBase
		   art::Framework_Core
		   art::Framework_Principal

		   art::Framework_Services_Registry
		   art_root_io::tfile_support ROOT::Core
		   art_root_io::TFileService_service
		   art::Persistency_Common
		   art::Persistency_Provenance
		   art::Utilities
                   canvas::canvas
		   messagefacility::MF_MessageLogger

		   fhiclcpp::fhiclcpp
		   cetlib::cetlib
                   cetlib_except::cetlib_except
		   ROOT::Geom
		   ROOT::XMLIO
		   ROOT::Gdml

          MODULE_LIBRARIES
                   lardataalg_DetectorInfo
		   larcorealg_Geometry
		   larcore_Geometry_Geometry_service
		   larsim_Simulation 
		   nug4::ParticleNavigation 
		   lardataobj_Simulation
		   nusimdata::SimulationBase
		   lardata_Utilities
		   lardataobj_MCBase
		   larcoreobj_SummaryData
		   lardataobj_RawData
		   lardataobj_RecoBase
		   lardata_RecoObjects
                   larevt_Filters
                   larevt_CalibrationDBI_IOVData
                   larevt_CalibrationDBI_Providers
		   nusimdata::SimulationBase
		   art::Framework_Core
		   art::Framework_Principal

		   art::Framework_Services_Registry
		   art_root_io::tfile_support ROOT::Core
		   art_root_io::TFileService_service
		   art::Persistency_Common
		   art::Persistency_Provenance
		   art::Utilities
                   canvas::canvas
		   messagefacility::MF_MessageLogger

		   fhiclcpp::fhiclcpp
		   cetlib::cetlib
                   cetlib_except::cetlib_except
		   ROOT::Geom
		   ROOT::XMLIO
		   ROOT::Gdml

		)


# install_headers()
#install_fhicl()
#install_source()
add_subdirectory(fcl)
