import React, { useState } from "react";
import { motion } from "framer-motion";

export default function SankalpYouthParliament() {
  const [selectedAgenda, setSelectedAgenda] = useState(null);

  const committees = [
    {
      name: "LOK SABHA",
      agenda:
        "Deliberation on the Role of the Waqf Board in a Secular Democracy: Scrutinizing Religious Land Autonomy in the Context of the Uniform Civil Code and Public Accountability."
    },
    {
      name: "RAJYA SABHA",
      agenda:
        "Deliberation on Structural Reforms in Indian Democracy: Evaluating the Implementation of One Nation One Vote, Caste-Based Census, and the Uniform Civil Code."
    },
    {
      name: "AIPPM",
      agenda:
        "Deliberation on the Indian Education System: Analyzing NEP 2020, Breaches in Examination Integrity, and the Ideological Influence of Marxism in Academic Curriculum."
    },
    {
      name: "JPC",
      agenda:
        "Deliberation on the Accountability of Constitutional Bodies, Electoral Reforms, and the Implications of the Special Intensive Revision (SIR) Process in Bihar."
    }
  ];

  const schedule = [
    "8:00 AM - Arrival and Registration",
    "9:00 AM - Opening Ceremony",
    "10:00 AM - Committee Sessions Begin",
    "1:00 PM - Lunch Break",
    "2:00 PM - Committee Sessions Resume",
    "5:00 PM - Closing Ceremony"
  ];

  const queries = [
    {
      question: "Is there a registration fee?",
      answer: "Yes, the registration fee is ₹399."
    },
    {
      question: "Can students from other schools register?",
      answer: "Yes, the event is open to all school students."
    },
    {
      question: "What is the dress code?",
      answer: "Participants are requested to wear school uniform or formal attire."
    },
    {
      question: "Will food be provided?",
      answer: "Yes, lunch and refreshments will be arranged."
    },
    {
      question: "Can we choose the committee we want to be in?",
      answer: "Yes, you can indicate your preference in the registration form."
    }
  ];

  return (
    <div className="min-h-screen bg-gradient-to-tr from-gray-100 to-white text-gray-800 font-sans">
      <header className="bg-white shadow-lg p-6">
        <div className="max-w-6xl mx-auto flex justify-between items-center">
          <div>
            <h1 className="text-3xl font-extrabold text-blue-900">
              Sankalp 2.0 Youth Parliament
            </h1>
            <p className="text-md text-gray-500 mt-1">
              <em>संकल्प ज्ञान का, संकल्प प्रगति का</em>
            </p>
          </div>
        </div>
      </header>

      <main className="max-w-5xl mx-auto px-4 py-6">
        {/* Register and Brochure */}
        <div className="flex flex-col md:flex-row justify-center gap-6 my-6">
          <a
            href="#"
            className="bg-gradient-to-r from-blue-600 to-indigo-600 text-white font-semibold py-3 px-8 rounded-xl shadow hover:scale-105 transition-all text-lg"
          >
            Register Now
          </a>
          <a
            href="#"
            className="border-2 border-indigo-500 text-indigo-700 font-medium py-3 px-8 rounded-xl hover:bg-indigo-50 hover:scale-105 transition-all text-lg"
          >
            View Brochure
          </a>
        </div>

        {/* About Us and Vision */}
        <section className="bg-white p-6 rounded-xl shadow-md mb-8">
          <h2 className="text-2xl font-bold text-indigo-800 mb-4">About Us</h2>
          <p className="text-gray-700 leading-relaxed">
            Sankalp 2.0 Youth Parliament is a student-led initiative organized by the enthusiastic youth of HGS. It provides a platform for students to engage in democratic simulations, understand policy making, and voice their thoughts on pressing national issues. Following the overwhelming success of our previous edition, Sankalp 2.0 brings bigger opportunities, deeper discussions, and a stronger voice for students.
          </p>
        </section>

        <section className="bg-white p-6 rounded-xl shadow-md mb-8">
          <h2 className="text-2xl font-bold text-indigo-800 mb-4">Our Vision</h2>
          <p className="text-gray-700 leading-relaxed">
            Our vision is to inculcate democratic values, develop leadership qualities, and foster critical thinking among school students. Sankalp Youth Parliament is committed to building informed citizens of tomorrow by encouraging meaningful debate and responsible civic engagement.
          </p>
        </section>

        {/* Committees Section */}
        <section className="my-8">
          <h2 className="text-3xl font-bold text-center text-indigo-800 mb-6">
            Committees
          </h2>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-6">
            {committees.map((committee) => (
              <motion.div
                key={committee.name}
                className="p-6 bg-white shadow-md rounded-xl border cursor-pointer hover:shadow-lg transition-all"
                onClick={() => setSelectedAgenda(committee)}
                whileHover={{ scale: 1.03 }}
              >
                <h3 className="text-xl font-semibold text-blue-700">
                  {committee.name}
                </h3>
              </motion.div>
            ))}
          </div>

          {selectedAgenda && (
            <motion.div
              className="mt-6 p-4 bg-blue-50 border-l-4 border-blue-400 text-blue-900 rounded shadow"
              initial={{ opacity: 0, y: 10 }}
              animate={{ opacity: 1, y: 0 }}
            >
              <h4 className="font-bold text-lg mb-2">
                Agenda for {selectedAgenda.name}:
              </h4>
              <p>{selectedAgenda.agenda}</p>
            </motion.div>
          )}
        </section>

        {/* Schedule Section */}
        <section className="my-8">
          <h2 className="text-2xl font-bold text-indigo-800 mb-4">Event Schedule</h2>
          <ul className="list-disc list-inside text-gray-700 space-y-1">
            {schedule.map((item, idx) => (
              <li key={idx}>{item}</li>
            ))}
          </ul>
        </section>

        {/* Queries */}
        <section className="my-10">
          <h2 className="text-2xl font-bold text-indigo-800 mb-4">
            General Queries
          </h2>
          <div className="space-y-4">
            {queries.map((q, idx) => (
              <div
                key={idx}
                className="bg-white border-l-4 border-indigo-400 shadow-md p-4 rounded"
              >
                <h4 className="font-semibold text-gray-800 mb-1">{q.question}</h4>
                <p className="text-gray-600">{q.answer}</p>
              </div>
            ))}
          </div>
        </section>

        {/* Contact */}
        <footer className="mt-16 border-t pt-6 text-center text-sm text-gray-600">
          <p>For any queries, reach us at:</p>
          <p className="font-semibold">sankalphgs@gmail.com</p>
        </footer>
      </main>
    </div>
  );
}
